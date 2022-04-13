# Audio-Steganography
  
Audio steganography is about hiding the secret message into the audio. It is a technique uses to secure the transmission of secret information or hide their existence. It also may provide confidentiality to secret message if the message is encrypted.

<h3>Algorithm</h3>

**Encoding**

• Reading the audio file using wave.open function to a variable cov_song  
• Secret message input from user  
• Converting the secret message to binary list  
• Reading frames from cov_song and convert to byte array, variable name 
of the byte array frm_bytes  
• Check if the length of the binary list is greater then the number of frames 
available in the audio file, then message cannot be encoded to the audio 
file and return 0 status, else continue to encode  
• For each character of the text 9 frame bytes values have taken from 
frm_bytes , LSB of each byte is used to store a single bit from the 
character bits.  
• The 9th frame determines if more frame bytes should be read or not. If 
there is more data to be read, i.e. encoded or decoded, then the ninth 
frame byte changes to even. Otherwise, if we want to stop reading frame 
byte further, then make it odd.  
• Writing the modifies bytes to a new Audio file  

**Decoding**

• Reading the embedded audio file using wave.open function to a variable 
embedded_song  
• Reading frames from embedded_song and convert to byte array, 
variable name of the byte array frm_byte  
• Iterating over the frm_byte array, extracting the data from LSB bits of 
first eight frames, converting that bit string to character and appending 
to a data. • Check for the 9th frame, if it is even then continue extracting the data, 
else stop extracting and return data.  

<h3>Steps to Execute the Code</h3>

1. Save the cover audio file in Google Drive, Save it under default 
MyDrive folder. (Don’t create any extra folder to store the audio file, else 
the path of the file will be changed, and the code won’t execute)  
Name the audio file as: <b> cover_audio.wav </b>
2. Run the code in colab, Enter the secret message  
3. After successfully execution of encode function, a new 
embedded.wav file will be created in the same google drive location  
4. After the message is encoded then you can run the decode function  
5. After the execution finishes, extracted message will be printed on 
the output.  
6. You can also listen to both the audio files in the colab and test the 
quality by listening  
