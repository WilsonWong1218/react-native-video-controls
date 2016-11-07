# react-native-video-controls
Controls for the React Native `<Video>` component at [react-native-video](https://github.com/react-native-community/react-native-video).

This has yet to be tested on Android.

![How it looks](https://s3-us-west-2.amazonaws.com/nubix.ca/github/example.gif)

## Installation
Run `npm install --save react-native-video-controls`
Install [rnpm](https://github.com/rnpm/rnpm) and run `rnpm link react-native-video-controls`

## Usage
The `<VideoPlayer>` component follows the API of the `<Video>` component at [react-native-video](https://github.com/react-native-community/react-native-video). It also takes a number of additional props which are outlined in the [API](#api) section.

For basic operation the `<VideoPlayer>` component requires a video source and a navigator property. The default back button functionality in the component pops the navigator. This can be overridden if desired, see the [API](#api) for more details.

```javascript
// At the top where our imports are...
import VideoPlayer from 'react-native-video-controls';


// in the components render() function
<VideoPlayer
    source={{ uri: 'https://vjs.zencdn.net/v/oceans.mp4' }}
    navigator={ this.props.navigator }
/>

```

## API
The `<VideoPlayer>` component can take a number of inputs to customize it as needed. They are outlined below:

```javascript
<VideoPlayer

    // react-native-video options
    playWhenInactive={ false }   // [iOS] continuing playing when notification centre active
    playInBackground={ false }   // play audio when entering background
    resizeMode={ 'contain' }     // 'contain' or 'cover' should be used.
    paused={ false }             // stop playback entirely
    volume={ 1 }                 // 0 is muted, 1 is normal.
    repeat={ false }             // Repeats at end of duration
    muted={ false }              // Mutes the audio entirely.
    title=""                     // Video title
    rate={ 1 }                   // 0 is paused, 1 is normal.

    // events
    onLoadStart={}   // Fired when loading of the source starts
    onProgress={}    // Fired every ~250ms when the video progresses
    onError={}       // Fired when an error is encountered on load
    onLoad={}        // Fired when loading is complete
    onEnd={}         // Fired when the video is complete.

    // actions
    goBack={}   // Function fired when back button is pressed.

/>
```