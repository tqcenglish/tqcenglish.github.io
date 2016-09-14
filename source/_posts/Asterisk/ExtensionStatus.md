# ExtensionStatus
AMI 分机状态事件，在分机进行响铃，注册等操作时会通过 AMI 抛出对应的事件. 通过命令
```
manager show event ExtensionStatus 
```
可以查看详细解释

```
Event: ExtensionStatus
[Synopsis]
Raised when a hint changes due to a device state change.

[Syntax]
Event: ExtensionStatus
Exten: <value>
Context: <value>
Hint: <value>
Status: <value>
StatusText: <value>

[Arguments]
Exten
    Name of the extension.
Context
    Context that owns the extension.
Hint
    Hint set for the extension
Status
    Numerical value of the extension status. Extension status is
    determined by the combined device state of all items contained in the
    hint.
    -2 - The extension was removed from the dialplan.
    -1 - The extension's hint was removed from the dialplan.
    0 - 'Idle' - Related device(s) are in an idle state.
    1 - 'InUse' - Related device(s) are in active calls but may take
    more calls.
    2 - 'Busy' - Related device(s) are in active calls and may not take
    any more calls.
    4 - 'Unavailable' - Related device(s) are not reachable.
    8 - 'Ringing' - Related device(s) are currently ringing.
    9 - 'InUse&Ringing' - Related device(s) are currently ringing and
    in active calls.
    16 - 'Hold' - Related device(s) are currently on hold.
    17 - 'InUse&Hold' - Related device(s) are currently on hold and in
    active calls.
StatusText
    Text representation of 'Status'.
    Idle
    InUse
    Busy
    Unavailable
    Ringing
    InUse&Ringing
    Hold
    InUse&Hold
    Unknown - Status does not match any of the above values.
```

**分机需要配置 hint**