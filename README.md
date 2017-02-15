# experiments
Nothing to see here. This is used for all kinds of experimentation and temporary work.

```cpp
struct Camera
{
	// Position of camera, in the game's coordinate space
	nv::Vec3 position;
	// Rotation of the camera, in the game's coordinate space. I.e. if you apply this
	// rotation to the default orientation of the game's camera you will get the current
	// orientation of the camera (again, in game's coordinate space)
	nv::Quat rotation;
	// Field of view in degrees. This value is either vertical or horizontal field of
	// view based on the 'fovType' setting passed in with setConfiguration.
	float fov;
	// The amount that the projection matrix needs to be offset by. These values are
	// applied directly as translations to the projection matrix. These values are only
	// non-zero during Highres capture.
	float projectionOffsetX, projectionOffsetY;
};

// Must be called on every frame an Ansel session is active. The 'camera' must contain
// the current display camera settings when called. After calling 'camera' will contain the
// new requested camera from Ansel.
ANSEL_SDK_API void updateCamera(Camera& camera);
``` 
