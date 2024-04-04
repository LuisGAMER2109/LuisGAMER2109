SetWindowCompositionAttribute.exe [hwnd <window handle> | name <window name> | class <window class name>] [blur <true/false> | accent <a1> <a2> <a3> <a4> | active <0/1> ] 

blur 	- true => enables blur behind windows (or fully opaque when Aero Glass effect is disabled)
	    - false => disables blur behind windows (= application-defined behaviour)
	    
accent	- a1 	= 0 => disables accent policy (= application-defined behaviour)
			 	= 1 => solid background
				= 2 => semi-transparent background
				= 3 => background is not drawn
		- a2	= 0 => semi-transparent alpha 0.5
				= 2 => semi-transparent alpha 0.75 (>= Win8.1 Update 1 only)
				= other values unknown
		- a3	= colour of solid background in format BBGGRR (e.g. ff0000 = blue colour)
		- a4	= valid values 0-5 (1 = animation during changing solid background colorm; other values currently unknown) 
		- other values are possible in original Win8, e.g. to change accent background image etc.
		
active	- 1 => forces active window appearance

Enable blur on taskbar:
	SetWindowCompositionAttribute.exe class Shell_TrayWnd accent 0 0 0 0
	SetWindowCompositionAttribute.exe class Shell_TrayWnd blur true
	
Default behaviour of taskbar:
	SetWindowCompositionAttribute.exe class Shell_TrayWnd blur false
	SetWindowCompositionAttribute.exe class Shell_TrayWnd accent 2 0 0 0