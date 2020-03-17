title: sails
date: 2018-09–02
tags: 
---

[原文链接](http://www.sailsjs.org/#!/documentation/concepts/Policies)

## 提要
Policies在Sails中作为授权和访问控制的通用工具.它让你可以去在粒度基本上控制允许或拒绝访问你的控制器。例如，如果你建立了一个Dropbox,在让用户上传文件到文件夹前，你需要检查用户是否认证，是否有写文件的权限，最后你要去检查用户上传内容的文件夹是否有足够的空间。

Policies可以用于任何方面:HTTP基本认证,第三方程序单点登录， OAuth 2.0, 自定义授权/认证方案。

**Policies只能用于控制器而不能用于视图。如果你在routes.js配置文件中定义了一个路由去直接指向视图，将没有Policies会起作用。为了确信policies是可用的，你可以定义一个控制器去显示试图并在路由中配置action**

## 实现你的第一个Policy
Policies是定义在你的Sails程序的api/policies文件夹下的文件。每一个policy文件应该包含一个函数。

当运行时，policies是在控制器前运行的中间件功能。你可以将中间件串联在一起使用,这也是被设计为这样使用。每一个中间件应该只完成一个功能。

例如，象上面提到的可写权限策略。

  //policies/canWrite.js
  module.exports = function canWrite (req, res, next){
  var targetFolderId = req.param('id');
  var userId = req.session.user.id;
  Permission
  .findOneByFolderId(targetFolderId)
  .exec( function foundPermission (err, permission) {
    //Unexpected error occurred -- skip to the app's default error(500) handler
    if(err) return next(err);
    //No permission exists linking this user to this folder. Maybe they got removed from it? Maybe they never had permission in the first place? Who cares?
    if(!permission) return res.redirect('/notAllowed');
    //Ok, so a permission was found. Let's be sure it's a  "write"
    if(permission.type !== 'write') return res.redirect('/notAllowed');
    //If we made it all the awy down here, looks like everything's ok. so we'll let the user through
    next();
    });
  };

##用Policies去保护控制器
Sails有内建一个ACL(访问控制表)位于config/policies.js文件。这个文件用于映射policies到你的控制器。

这个文件是声明，它描述了你的应用权限应该是什么，并不描述它是如何实现。这使得新开发者更容易的去理解发生了什么事。另外让你的应用更灵活因为你的要求是不可避免的不断改变。

你的config/policies.js文件应该导出一个Javascript对象，它的键名是控制器的名称(或'*'用于全部的policies).它的值是对象映射的操作名称和一个或多个policies.看下面获取更详细的说明和例子说明。

###应用一个policy到指定的控制器操作

  {
    ProfileController:{
      //Apply the 'isLoggedIn' policy to the 'edit' action of 'ProfileController'
      edit:'isLoggedIn'
      //Apply the 'isAdmin' And 'isLoggedIn' policies , in the order, to the 'create' action
      create:[isAdmin', 'isLoggedIn']
    }

  }

###应用一个policy到整个控制器

  {
    ProfileController:{
    //Apply 'isLogged' in by default to all actions that are Not specied below
    '*': 'isLoggedIn',
    //If an action is explicitly listed, its policy list will override the default list
    //So, we have to list 'isLoggedIn' again for the 'edit' action if we want it to be applied
    edit: ['isAdmin', 'isLoggedIn']
  }

**默认的策略映射不会"cascade"或"trickle down", 对于控制器的操作指定的策略映射会覆盖默认的映射**

> 这是一般 Sails 关于权限控制的官方文档翻译。 后面再说吧。
