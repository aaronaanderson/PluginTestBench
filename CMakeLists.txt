cmake_minimum_required(VERSION 3.15)

project(PLUGIN_TEST_BENCH VERSION 0.0.1)

add_subdirectory(JUCE)

juce_add_gui_app(PluginTestBench
    VERSION "0.0.1"
    PRODUCT_NAME "Plugin Test Bench"
    MICROPHONE_PERMISSION_ENABLED   TRUE
    PLUGINHOST_AU                   TRUE)

juce_generate_juce_header(PluginTestBench)

target_sources(PluginTestBench PRIVATE
    Source/Main.cpp
    Source/MainComponent.cpp)

target_compile_definitions(PluginTestBench PRIVATE
    JUCE_ALSA=1
    JUCE_DIRECTSOUND=1
    JUCE_PLUGINHOST_LADSPA=1
    JUCE_PLUGINHOST_VST3=1
    JUCE_PLUGINHOST_VST=0
    JUCE_USE_CAMERA=0
    JUCE_USE_CDBURNER=0
    JUCE_USE_CDREADER=0
    JUCE_USE_CURL=0
    JUCE_USE_FLAC=0
    JUCE_USE_OGGVORBIS=1
    JUCE_VST3_HOST_CROSS_PLATFORM_UID=1
    JUCE_WASAPI=1
    JUCE_WEB_BROWSER=0
    JUCE_APPLICATION_NAME_STRING="$<TARGET_PROPERTY:PluginTestBench,JUCE_PRODUCT_NAME>"
    JUCE_APPLICATION_VERSION_STRING="$<TARGET_PROPERTY:PluginTestBench,JUCE_VERSION>"
    JUCE_DISPLAY_SPLASH_SCREEN=0
    )

target_link_libraries(PluginTestBench PRIVATE
    juce::juce_audio_utils
    juce::juce_cryptography
    juce::juce_dsp
    juce::juce_opengl
    juce::juce_recommended_config_flags
    juce::juce_recommended_lto_flags
    juce::juce_recommended_warning_flags)
