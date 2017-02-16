# experiments
Nothing to see here. This is used for all kinds of experimentation and temporary work.

```cpp
enum CaptureType
{
	kCaptureType360Mono = 0,
	kCaptureType360Stereo,
	kCaptureTypeSuperResolution,
	kCaptureTypeStereo
};

struct CaptureConfiguration
{
	CaptureType captureType;
};

typedef void(*StartCaptureCallback)(const CaptureConfiguration&, void* userPointer);
typedef void(*StopCaptureCallback)(void* userPointer);
``` 
