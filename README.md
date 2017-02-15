# experiments
Nothing to see here. This is used for all kinds of experimentation and temporary work.

```cpp
enum SetConfigurationStatus
{
  // successfully initialized the Ansel SDK
  kSetConfigurationSuccess,

  // the version provided in the Configuration structure is not the same as the one stored       
  // inside the SDK binary (header/binary mismatch)
  kSetConfigurationIncompatibleVersion,
        
  // the Configuration structure supplied for the setConfiguration call is not consistent
  kSetConfigurationIncorrectConfiguration,
        
  // the Ansel SDK is delay loaded and setConfiguration is called before the SDK is actually loaded
  kSetConfigurationSdkNotLoaded
};

// Called during startup by the game. See 'Configuration' for further documentation.
ANSEL_SDK_API SetConfigurationStatus setConfiguration(const Configuration& cfg);   
``` 
