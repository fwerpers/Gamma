set (
	SRCS
	AudioIO.cpp
	SoundFile.cpp 
	arr.cpp
	Conversion.cpp
	Domain.cpp
	DFT.cpp
	FFT_fftpack.cpp
	fftpack++1.cpp
	fftpack++2.cpp
	Print.cpp
	scl.cpp
	Recorder.cpp
	Scheduler.cpp
	Timer.cpp)

add_library(audio_io AudioIO.cpp)
target_link_libraries(audio_io portaudio ${SND_LIBRARY})

add_library(gamma STATIC ${SRCS})
