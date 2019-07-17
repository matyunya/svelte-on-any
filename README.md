# Svelte on any

Svelte on any is a tiny preprocessor which helps to forward all DOM events.

### Installation
```
yarn add svelte-on-any
```

In your `rollup.config.js` add `onAny` to preprocess section:

```
import onAny from "svelte-on-any";


svelte({
  preprocess: {
    ...onAny(),
  }
})
```

Now all you have to do is put `on:any` on your element!
```
<button on:any>
```
Will generate
```
<button on:mouseenter on:mouseleave... >
```

### Configuration and defaults

On-any accepts one argument which is a function called on the list of events.

```
// Forward only events that contain "mouse" in their name
onAny(events => events.filter(event => event.includes('mouse')))
```

### List of events
- readystatechange
- mouseenter
- mouseleave
- wheel
- copy
- cut
- paste
- beforescriptexecute
- afterscriptexecute
- abort
- canplay
- canplaythrough
- change
- click
- contextmenu
- dblclick
- drag
- dragend
- dragenter
- dragleave
- dragover
- dragstart
- drop
- durationchange
- emptied
- ended
- input
- invalid
- keydown
- keypress
- keyup
- loadeddata
- loadedmetadata
- loadstart
- mousedown
- mousemove
- mouseout
- mouseover
- mouseup
- pause
- play
- playing
- progress
- ratechange
- reset
- seeked
- seeking
- select
- show
- stalled
- submit
- suspend
- timeupdate
- volumechange
- waiting
- mozfullscreenchange
- mozfullscreenerror
- mozpointerlockchange
- mozpointerlockerror
- blur
- error
- focus
- load
- scroll

Feedback and feature requests are welcome!