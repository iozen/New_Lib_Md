
#python #voice_to_text

~~~bash 
pip install SpeechRecognition
~~~

~~~python 

import speech_recognition as sr
r = sr.Recognizer()


file_path = "path/to/audio/file.wav" 
with sr.AudioFile(file_path) as source: 
	audio = r.record(source)

try:
    # Recognize speech using Google Speech Recognition
    text = r.recognize_google(audio)
    print("You said:", text)
except sr.UnknownValueError:
    print("Sorry, I could not understand your speech")
except sr.RequestError as e:
    print("Sorry, an error occurred while retrieving results from Google Speech Recognition:", str(e))

~~~