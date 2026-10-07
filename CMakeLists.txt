cmake_minimum_required(VERSION 3.22)

project(DenmanVocalProcessor VERSION 1.0.0)

set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

add_subdirectory(JUCE)

juce_add_plugin(DenmanVocalProcessor
    COMPANY_NAME "Denman Sounds"
    PLUGIN_MANUFACTURER_CODE DmSn
    PLUGIN_CODE DVP1
    FORMATS VST3 Standalone
    PRODUCT_NAME "Denman Vocal Processor"
)

target_sources(DenmanVocalProcessor
    PRIVATE
        Source/PluginProcessor.cpp
        Source/PluginProcessor.h
        Source/PluginEditor.cpp
        Source/PluginEditor.h
)

target_link_libraries(DenmanVocalProcessor
    PRIVATE
        juce::juce_audio_utils
        juce::juce_dsp
)
