# Svelte on any [DEPRECATED]

Svelte on any is a tiny preprocessor which helps to forward all DOM events.

This in fact is not a good way to forward events since it would attach event listeners for every single event, which is a big performance handicap so please don't use it unless you absolutely have to.

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
- abort
- afterscriptexecute
- auxclick
- beforescriptexecute
- blur
- canplay
- canplaythrough
- change
- click
- contextmenu
- copy
- cut
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
- error
- focus
- fullscreenchange
- fullscreenerror
- gotpointercapture
- input
- invalid
- keydown
- keypress
- keyup
- load
- loadeddata
- loadedmetadata
- loadstart
- lostpointercapture
- mousedown
- mouseenter
- mouseleave
- mousemove
- mouseout
- mouseover
- mouseup
- mozfullscreenchange
- mozfullscreenerror
- mozpointerlockchange
- mozpointerlockerror
- paste
- pause
- play
- playing
- pointercancel
- pointerdown
- pointerenter
- pointerleave
- pointerlockchange
- pointerlockerror
- pointermove
- pointerout
- pointerover
- pointerup
- progress
- ratechange
- readystatechange
- reset
- scroll
- seeked
- seeking
- select
- show
- stalled
- submit
- suspend
- timeupdate
- touchcancel
- touchend
- touchmove
- touchstart
- volumechange
- waiting
- wheel

Feedback and feature requests are welcome!
