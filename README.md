# Music-Note-Recognition
MATLAB project for recognizing music notes from an input audio file


1.1	OBJECTIVES AND GOALS

Design a musical note recognition software using MATLAB.
It can identify the exact note by finding the frequency of the input note.



1.2 	ABSTRACT

Music is an integral part of everyone’s lives. Music helps in relaxation, therapy and entertainment. The audio industry is booming with online platforms for music streaming. This program helps identify the musical notes in a piece of audio and gives valuable information about its pitch, frequency and type. The music piece fed to the system can be decoded to identify which note the signal corresponds to.


1.3 FEATURES

-  Effective use of Fast Fourier Transform to determine   frequency
-  Can be used for audio matching
-  Decode the musical note type for any unknown audio signal


1.4 DESIGN

The musical piece is fed to the system which processes the audio signal and recognizes the frequency and pitch of the signal thereby identifying the type of musical note by comparing it with the standard musical notes available.



1.5 	SOFTWARE ANALYSIS

The process used for this project can be described in six different stages. 
1) The first step involves the input of a sequence of desired musical note whose frequency is to be found. The sequence of sounds are digitally recorded. 

2) In the second step, the signal is analyzed using Matlab. In Matlab, the series of notes are initially plotted in the time domain.

3) The third step requires more of analysis and programming. We designed a windowing technique that determines the window of each note in the sequence.  This technique first involved a method to determine when a note begins and ends.
This program takes in a double array specified by the data and outputs a vector of division points that correspond to separate and distinct notes. In other words, trying to find when one note stops and another starts. The returned vector will include the midpoint of the end of note and the beginning of the next. It can be easily noticed in a note sequence that there is a visible drop in energy between notes i.e. a small gap from one note to another note. This fact is used in determining the actual window of a note.

4) The fourth step involves the analysis of the signal in the frequency domain.  Now as that the windows of each note have been determined in the step above mentioned, each individual note is converted to the frequency domain. Hence, here comes the application of fast fourier series to get the frequency domain of our input signal.


FAST FOURIER TRANSFORM
The fast Fourier transform (FFT) is a discrete Fourier transform algorithm which reduces the number of computations needed for  points from  to , where log is the base-2 logarithm.


5) The fifth step involves determining the fundamental frequency of each note.  A standard musical note played by standard instruments is described by a fundamental frequency, which is the maximum frequency, along with other smaller harmonics.  Therefore, to determine the fundamental frequency, find the maximum frequency for each signal.

6) Finally, To determine the actual note, we find the pitch of the note using the following method. Based on the frequency of the pitches in the middle C octave, the octave above middle C, the program determines whether the input frequency is above or below this range. 

If the frequency is below the middle C octave range it multiplies the input frequency by 2, adds one to a counter that keeps track of how many times the process has recurred and then calls the process on the input frequency times 2.

If the frequency is above the middle C octave range it divides the input frequency by 2 and goes through the same process but now it divides by 2 instead of multiplying. 

If the frequency is in the middle C octave range it determines what pitch it is based on some accepted ranges/values for pitches and return the pitch. Finally, the program returns the pitch and the octave above or below the middle C octave.  (Positive for octaves above, negative for octaves below).



1.6    CONCLUSION

In our project, we designed and implemented an effective and user-friendly frequency estimation system with Fourier Analysis. 

The target users of the system are not only the people practicing music, but also professional musicians who cannot waste their time figuring out the notes of an audio sample.




1.7    FUTURE WORK
There is still much room for future development that would enhance the system and increase its usage value. The following items are some suggestions:

Advanced Note Detection: 
There are lot of ways we to improve and customize note detection. Most of them use variations in intensity, which is not the right way because strictly speaking a note is said to change when the frequency of the signal changes. It is not easy to keep track of change in frequency because the change is gradual and hence it is an existing challenge. Moreover the frequency estimation for calculating note detection requires note detection in a crude sense which is paves way for development in this area.

Non Periodic Signal analysis: 
The process is relatively simple if the signal were sinusoidal or periodic. But the real life musical notes or vocals are approximately periodic and the frequency itself changes with time because a sample may contain more than one note and that is how music is played. While Fourier Analysis is a nice solution to this problem, it is not sufficient. Theoretically it may be sufficient but its high level implementation is not as there is resolution and run time limit. There is scope to overcome latter by designing algorithms especially for the purpose of frequency estimation and not focusing on phase detection.

Multiple Notes at a time: 
Our project assumes that only a single note is played at a time. But that is not it. We can develop it further by using Fourier Analysis again. There are existing algorithms which can isolate multiple notes. After splitting the audio sample into individual notes we can apply our own techniques to find the frequency.



1.8   REFERENCES


www.google.com

www.wikipedia.com 

https://www.clear.rice.edu

https://in.mathworks.com/matlabcentral/fileexchange







