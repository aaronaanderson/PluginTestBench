# Plugin Test Bench

An audio plugin host designed to run and test plugins as you build them. 

None of it exists yet; it's just a bare cmake JUCE build build at the moment

Goals;

Run on Linux, Windows, and MacOS.
Host VST3, VST(2), Audio Unit, and AAX format plugins

Display the plugin
Bare-bones automation lanes for each parameter.
Simple unit generators (and soundfile player) to feed in to the plugin
Simple MIDI note loops to feed into instrument plugins

File watcher that runs in the background; if a plugin is loaded and the file is updated, the app will automatically load the new version.

Ability to attach debugger