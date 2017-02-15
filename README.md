# experiments
Nothing to see here. This is used for all kinds of experimentation and temporary work.

```cpp
struct Configuration
{
	// Basis vectors used by the game. They specify the handedness and orientation of 
	// the game's coordinate system. Think of them as the default orientation of the game
	// camera.
	nv::Vec3 right, up, forward;
	// The speed at which camera moves in the world
	float translationalSpeedInWorldUnitsPerSecond;
	// The speed at which camera rotates 
	float rotationalSpeedInDegreesPerSecond;
	// How many frames it takes for camera update to be reflected in a rendered frame
	uint32_t captureLatency;
	// How many frames we must wait for a new frame to settle - i.e. temporal AA and similar
	// effects to stabilize after the camera has been adjusted
	uint32_t captureSettleLatency;
	// Game scale, the size of a world unit measured in meters
	float metersInWorldUnit;
	// Integration will support Camera::projectionOffsetX/projectionOffsetY
	bool isCameraOffcenteredProjectionSupported;
	// Integration will support Camera::position
	bool isCameraTranslationSupported;
	// Integration will support Camera::rotation
	bool isCameraRotationSupported;
	// Etc ...
``` 
