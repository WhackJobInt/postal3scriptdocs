# Changelog for Postal3Script Docs

This is the changelog for Postal3Script docs, because we make mistakes and some functions might not work the way we initially defined them in descriptions.

If you have any issues related to Postal3Script Docs, let us know <a href="https://github.com/WhackJobInt/Postal3ScriptDocsTracker/issues">here</a> by opening a new issue.

## 17.10.2022

- Rewrote "Ignore" page, it checks if a pointer was already ignored, and not that it sets ignoring.
- Added "Anchor, TargetAnchor" page.
- Updated the Gestures page to have "Sequence" function
- Updated "Wait, WaitForEnd, Repeat" page to have "Return" function
- Added "ea_gibs" to "Embedded Attributes" page
- Updated "AreaEvent" note

## 07.10.2022

- Description of CheckAttr corrected, it checks if an attribute exists or not (was created via SetAttr before), and not if it's 0 or 1.
- Added AreaEvent page, seperated it from Fire functions in Misc functions.
- Added Call to "CallState, CallPattern, Call" page, marking the whole page as complete.
- Added "SendState, SendPattern" page, it is complete.
- Updated "StateMatrix" page to have example code from ai_matrix.p3s.
- Updated "Embedded Attributes" page to be much more precise in terms of descriptions.

## 30.08.2022

- Added Debugging page, which explains debugging Postal3Script.
- Corrected ChangeAttr description, working between 0-100 values is <b>not a bug</b>, minimum and 
maximum values need to be set via SetAttr.
- Corrected Postal3Script limitation explanations.
- Fixed missing href for "Gesture, ResetGesture, ResetSequence" on index page.