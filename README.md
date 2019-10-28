# tbkeys

`tbkeys` is a bootstrapped extension for Thunderbird that uses
[Mousetrap](https://craig.is/killing/mice) to bind key sequences to custom
commands. Currently, it supports no customization and has hard-coded
keybindings similar to the ones available in Google's GMail web app.
[dorando-keyconfig](https://github.com/trlkly/dorando-keyconfig) is an example
of an extension that allows custom keybindings and supports customization but
does not currently work with Thunderbird 68.

## Current keybindings

| Key | Function |
| --- | -------- |
|  r  | Reply |
|  shft+r  | Reply all |
|   l | Toggle Folder List Pane |
| alt+f8| Toggle Message Pane |



## Info on keybindings

For modifier keys you can use `shift`, `ctrl`, `alt`, or `meta`.  More info can be found here: https://craig.is/killing/mice
Function keys supported with lower case `f` (e.g. `f8`, `f12`)

For a trick to see what the target action is (`<keyset>` and `<key>` elements) see here: http://forums.mozillazine.org/viewtopic.php?p=14845675#p14845675

```
setTimeout(function () {
  function getCommand(event) {
    window.removeEventListener("command", getCommand, true);
    event.preventDefault();
    event.stopPropagation();
    console.log(event.originalTarget.parentElement);
    console.log(event.originalTarget);
    console.log("event listener is removed");
    Services.wm.getMostRecentWindow("devtools:webconsole").focus();
  }
  window.addEventListener("command", getCommand, true);
  console.log("event listener is added");
}, 2000);
```
