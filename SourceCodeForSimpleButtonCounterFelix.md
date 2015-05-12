#Source Code for Simple Button Counter

# Introduction #

Simple Up/Down Counter to increment or decrement number upto a target limit.


# Source Code #
```
/*
*Name:Simple Button Counter
*Author:Ashok Felix
*Website: www.ashok88.com
*Copyright: Free to use, modify and distribute. No Conditions :)
*/
#SingleInstance Off
Gui, Font, S60 CDefault Bold, Verdana
Gui, Add, Button, x166 y150 w120 h100 , -
Gui, Font, S20 CDefault Bold, Verdana
Gui, Add, Button, x26 y260 w130 h40 , Reset
Gui, Font, S7 , 
Gui, Add, Text, x170 y260 w60 h20 , Max Limit
Gui, Add, Text, x240 y260 w60 h20 , Target
Gui, Font, S10 CDefault , Verdana
Gui, Add, Edit, x170 y280 w60 h20 vMaxLimit Number, 100
Gui, Add, Edit, x240 y280 w50 h20 vTarget Number, 100
Gui, Font, , 
Gui, Add, Text, Center x16 y350 w270 h40 gSourceCode, © Ashok Felix - Simple Button Counter 
 Click here for Source
Gui, Font, S60 Bold, 
Gui, Add, Button, Default x26 y150 w130 h100 , +
Gui, Font, S60 Bold, 
Gui, Add, Text, vCounter x16 y20 w270 h120 Center, 0
Gui, Add, Slider, x16 y310 w270 h30 vMySlider gSlideCounter AltSubmit
Gui, Font, , 
Gui, Show, h390 w306 Center, Simple Button Counter - Felix
Gui, Submit , NoHide
Return

Button+:
GuiControlGet, Counter
GuiControlGet, Target
Counter+=1
GuiControl,Text,Counter,-7
if(Counter==Target){
        MsgBox, You have reached your TARGET :)
}
GuiControlGet, MySlider
GuiControlGet, MaxLimit
maxLimitValue=100

Counter:=(Counter/maxLimitValue)*100
roundedCounter:=Round(Counter)
GuiControl,,MySlider,-7
return


Button-:
GuiControlGet, Counter
GuiControlGet, Target
Counter-=1
GuiControl,Text,Counter,-7
if(Counter==Target){
        MsgBox, You have reached your TARGET :)
}
GuiControlGet, MySlider
GuiControlGet, MaxLimit
maxLimitValue=100
Counter:=(Counter/maxLimitValue)*100
roundedCounter:=Round(Counter)
GuiControl,,MySlider,-7
return

ButtonReset:
resetValue=0
GuiControlGet, Counter
GuiControlGet, MySlider
GuiControl,,MySlider,0
GuiControl,Text,Counter,0
return

SlideCounter:
GuiControlGet, MySlider
sliderValue=0
GuiControlGet, MaxLimit
maxLimitValue=100
sliderValue*=(maxLimitValue//100)
GuiControl,Text,Counter,0
return

SourceCode:
Gui, 2:+owner1  
Gui, 2:Add, Edit, w500 h550 ReadOnly VScroll , Source Code for this Application Goes here.
Gui, 2:Show
return

GuiClose:
ExitApp

```