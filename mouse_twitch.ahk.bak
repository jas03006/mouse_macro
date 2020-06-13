#Include AutoHotkey-JSON-master\JSON.ahk
#SingleInstance Force
#Persistent
#NoEnv  ; Recommended for performance and compatibility with future AutoHotkey releases.
; #Warn  ; Enable warnings to assist with detecting common errors.
SendMode Input  ; Recommended for new scripts due to its superior speed and reliability.
SetWorkingDir %A_ScriptDir%  ; Ensures a consistent starting directory.
CoordMode, Mouse, Screen
FileRead, data, setting.json

pos_data := JSON.Load(data)
L_X := pos_data["left_monitor_X"]
L_Y := pos_data["left_monitor_Y"]
R_X := pos_data["right_monitor_X"]
R_Y := pos_data["right_monitor_Y"]

flag := 0

MsgBox, Restart (Pause): F1`nMode Select: F2, F3, F4`n- F2: Dual Monitor`n- F3: Main Monitor (right-side monitor)`n- F4: Sub Monitor (left-side monitor)`nExit: Esc

Loop{
	Sleep, 1000
	if(flag == 1){
		MouseClick, L, R_X, R_Y, 1, 0
		Sleep, 1000
		MouseClick, L, L_X, L_Y, 1, 0
	}else if(flag == 2){
		MouseClick, L, R_X, R_Y, 1, 0
		Sleep, 1000
		MouseMove, R_X+50, R_Y+5, 0
	}else if(flag == 3){
		MouseClick, L, L_X, L_Y, 1, 0
		Sleep, 1000
		MouseMove, L_X+50, L_Y+5, 0
	}
}


F2::
	MsgBox, Dual Monitor Mode
	flag = 1
return

F3::
	MsgBox, Main Monitor Mode
	flag = 2
return

F4::
	MsgBox, Sub Monitor Mode
	flag = 3
return

F1::
	reload
return

Esc::
	ExitApp
return