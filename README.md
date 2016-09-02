# TextAppearanceSpanCrash

A small test project to reproduce a crash in TextAppearanceSpan.

To reproduce:

* Launch the app on a Nexus 5X with the Nougat system
* The app is just an EditText, type some text there until the spell checker activates and underlines a word.
* Click the word to show the suggestions from the spellchecker
* It should crash with the backstack below:

```
         java.lang.UnsupportedOperationException: Failed to resolve attribute at index 6: TypedValue{t=0x2/d=0x101009b a=1}
             at android.content.res.TypedArray.getColorStateList(TypedArray.java:528)
             at android.text.style.TextAppearanceSpan.<init>(TextAppearanceSpan.java:65)
             at android.text.style.TextAppearanceSpan.<init>(TextAppearanceSpan.java:45)
             at android.widget.Editor$SuggestionsPopupWindow.setUp(Editor.java:3316)
             at android.widget.Editor$PinnedPopupWindow.<init>(Editor.java:3016)
             at android.widget.Editor$SuggestionsPopupWindow.<init>(Editor.java:3309)
             at android.widget.Editor.replace(Editor.java:356)
             at android.widget.Editor$3.run(Editor.java:2129)
             at android.os.Handler.handleCallback(Handler.java:751)
             at android.os.Handler.dispatchMessage(Handler.java:95)
             at android.os.Looper.loop(Looper.java:154)
             at android.app.ActivityThread.main(ActivityThread.java:6077)
             at java.lang.reflect.Method.invoke(Native Method)
             at com.android.internal.os.ZygoteInit$MethodAndArgsCaller.run(ZygoteInit.java:865)
             at com.android.internal.os.ZygoteInit.main(ZygoteInit.java:755)
```
