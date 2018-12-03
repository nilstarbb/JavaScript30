# 01 - JavaScript Drum Kit

LIVE DEMO: <https://serenaliaojc.github.io/JavaScript30/01-JavaScript-Drum-Kit/index-SERENA.html>

Image origin: https://www.pexels.com/photo/close-up-photo-of-drum-set-995301/



## Key Concepts

1. **JavaScript EventListener**

The `addEventListener()` method attaches an event handler to the specified element.

`element.addEventListener(event, function, useCapture);`

`transitionend`: The event occurs when a CSS transition has completed.

`keydown`: The event occurs when the user is pressing a key

2. **CSS transition**

CSS transitions allows you to change property values smoothly (from one value to another), over a given duration.

`transition: property duration timing-function delay|initial|inherit;`

3. **Key Code**

Every key on the keyboard associates with a specific number, which is known as key code.

4. **Custom HTML Attributes**

Use the `data-*` attribute to embed custom data.

Custom attributes prefixed with "`data-`" will be completely ignored by the user agent.

5. `audio` element



## Additional Changes

1. Replace letters with numbers and use `key` instead of `keyCode` for better user experience.

   Now you can play by pressing number keys from both typewriter and numeric pad.

2. Add `click` function. 

   Now you can click to play.

3. Add extra styles.

   1. Add hover effect.
   2. Apply `flex-wrap: wrap` when the screen width is 850px or less.



## Steps

1. Replace letters with numbers and use `key` instead of `keyCode` for better user experience.

   ```
   <div data-key="1" class="key">
     <kbd>1</kbd>
     <span class="sound">clap</span>
   </div>
   
   const pressedKey = document.querySelector('div[data-key="'+e.key+'"]');
   ```

2. Add `click` function. 

   ```
   function clickSound() {
       const clickedKey = this.getAttribute('data-key');
       const audio = document.querySelector('audio[data-key="'+clickedKey+'"]');
       if (!audio) return;
       this.classList.add('playing');
       audio.currentTime = 0;
       audio.play();
   }
   key.addEventListener('click', clickSound);
   ```

3. Add extra styles.

   1. Add hover effect.

      ```
      .key:hover {
          border-color: #ffc600;
          cursor: pointer;
          user-select: none;
        }
      ```

   2. Apply `flex-wrap: wrap` when the screen width is 850px or less.

      ```
      @media all and (max-width: 850px) {
          .keys {
              flex-wrap: wrap;
          }
      }
      ```


