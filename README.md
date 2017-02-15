# experiments
Nothing to see here. This is used for all kinds of experimentation and temporary work.

```cpp
struct Configuration
{  
	// Called when user activates Ansel. Return kDisallowed if the game cannot comply with the
	// request. If the function returns kAllowed the following must be done:
	// 1. Change the SessionConfigruation settings, but only where you need to (the object
	//    is already populated with default settings).
	// 2. On the next update loop the game will be in an Ansel session. During an Ansel session 
    //    the game :
	//    a) Must stop drawing UI and HUD elements on the screen, including mouse cursor
    //    b) Must call ansel::updateCamera on every frame
 	//    c) Should pause rendering time (i.e. no movement should be visible in the world)
  	//    d) Should not act on any input from mouse and keyboard and must not act on any input 
  	//       from gamepads
	// 3. Step 2 is repeated on every iteration of update loop until Session is stopped.
	StartSessionCallback startSessionCallback;

	// Called when Ansel is deactivated. This call will only be made if the previous call
	// to the startSessionCallback returned kAllowed.
	// Normally games will use this callback to restore their camera to the settings it had 
	// when the Ansel session was started.
	StopSessionCallback stopSessionCallback;
}
``` 
