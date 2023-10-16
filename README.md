# office-extension

A copy of Google's office extension

Hosted here incase google takes their extension down.

Extension [link](https://chrome.google.com/webstore/detail/office-editing-for-docs-s/gbkeegbaiigmenfmjfclcdgdpimamgkj/related?hl=en-GB)

## What it does

It lets you open local office files in the browser, without google drive, or even a google account!
It was made for the chromebook originally, I guess. Had to stumble across it to find it.

Just register your browser as the app to open office files and it will open it as a `file:` URL and just work.
It will also open office files at remote URLs. Uses google's office suite's rendering engine so should have decent support for office formats.

Editing and saving as docx is always iffy and won't work for complex usecases similar to every
other non microsoft tool, and you might have to move it to google docs for that (single click in the extension)

Powerpoint and excel work great as well, as far as I have seen.

## How to add to browser

 - Download the file in this repository
 - `cat office.tar.gz | gunzip | tar -x` on linux and macos (7zip should handle it fine on windows)
 - In your browser, go to `about:extensions`, enable developer mode, click on "Load Unpacked" and choose the folder that just got created (147.whatever)
 - If opening files doesn't work now, check the browser logs, if there are errors with "onChange" or something like that, then you have to
   go to `about:flags/#navigator-connection-attribute` in your browser, set it to enabled, and close and reopen your browser twice (I don't know why twice,
   but that's what worked, probably the extension caching something). Read https://github.com/brave/brave-browser/issues/20122 to know why
   it is disabled by default. You might want to trade off this extension for the benefits outlined in that link.

I only tested on chromium related browsers. It might work on firefox as well if you change the manifest. I might do this later.
