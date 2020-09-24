<div align="center">

## Stay on Top \(Fixed\)


</div>

### Description

I'm not sure sure if it's just my computer but, for some reason, my VB programs never stay on top of other windows all the time when I use the SetWindowPos API. This program still uses the SetWindowPos API but I added some stuff to make it work properly.
 
### More Info
 


<span>             |<span>
---                |---
**Submitted On**   |
**By**             |[VB Beginner](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByAuthor/vb-beginner.md)
**Level**          |Beginner
**User Rating**    |4.0 (8 globes from 2 users)
**Compatibility**  |VB 6\.0
**Category**       |[Miscellaneous](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByCategory/miscellaneous__1-1.md)
**World**          |[Visual Basic](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByWorld/visual-basic.md)
**Archive File**   |[](https://github.com/Planet-Source-Code/vb-beginner-stay-on-top-fixed__1-58463/archive/master.zip)





### Source Code

```
Option Explicit
Private Declare Function GetActiveWindow Lib "user32" () As Long
Private Declare Function SetWindowPos Lib "user32" (ByVal hWnd As Long, ByVal hWndInsertAfter As Long, ByVal x As Long, ByVal Y As Long, ByVal cx As Long, ByVal cy As Long, ByVal wFlags As Long) As Long
Private Const HWND_TOPMOST = -1 'bring to top and stay there
Private Const SWP_NOMOVE = &H2 'don't move window
Private Const SWP_NOSIZE = &H1 'don't size window
Private Sub Form_Load()
Call SetWindowPos(hWnd, HWND_TOPMOST, 0, 0, 0, 0, SWP_NOMOVE Or SWP_NOSIZE)
End Sub
Private Sub Timer1_Timer()
'If I remove the "If GetActiveWindow = 0 then" portion, then the form will also go on top of context menus, also
If GetActiveWindow = 0 Then
Call SetWindowPos(hWnd, HWND_TOPMOST, 0, 0, 0, 0, SWP_NOMOVE Or SWP_NOSIZE)
End If
End Sub
```

