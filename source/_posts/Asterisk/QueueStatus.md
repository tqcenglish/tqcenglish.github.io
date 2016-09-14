# QueueMemberStatus
主动事件，当队列中成员发生变化时(例如接听电话)产生

```
manager show event QueueMemberStatus 
```


```
Event: QueueMemberStatus
[Synopsis]
Raised when a Queue member's status has changed.

[Syntax]
Event: QueueMemberStatus
Queue: <value>
MemberName: <value>
Interface: <value>
StateInterface: <value>
Membership: <value>
Penalty: <value>
CallsTaken: <value>
LastCall: <value>
Status: <value>
Paused: <value>
Ringinuse: <value>

[Arguments]
Queue
    The name of the queue.
MemberName
    The name of the queue member.
Interface
    The queue member's channel technology or location.
StateInterface
    Channel technology or location from which to read device state
    changes.
Membership
    dynamic
    realtime
    static
Penalty
    The penalty associated with the queue member.
CallsTaken
    The number of calls this queue member has serviced.
LastCall
    The time this member last took a call, expressed in seconds since
    00:00, Jan 1, 1970 UTC.
Status
    The numeric device state status of the queue member.
    0 - AST_DEVICE_UNKNOWN
    1 - AST_DEVICE_NOT_INUSE
    2 - AST_DEVICE_INUSE
    3 - AST_DEVICE_BUSY
    4 - AST_DEVICE_INVALID
    5 - AST_DEVICE_UNAVAILABLE
    6 - AST_DEVICE_RINGING
    7 - AST_DEVICE_RINGINUSE
    8 - AST_DEVICE_ONHOLD
Paused
    0
    1
Ringinuse
    0
    1
```    