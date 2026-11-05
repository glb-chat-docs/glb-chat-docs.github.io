# Section 1 - insides

## 1.1 - cloud variable limits

NTT and TTN serve a crucial role in the process of sending messages, because cloud variables can only store numbers, these convert your text into numbers through the CHAR_KEY, using the number placement of the letter (and vice-versa) to encrypt & decrypt messages.

Usernames are sent through a seperate username cloud variable, to keep the message limit a clean 128 characters

The message limit is 128 characters because cloud variables can only store up to 256 numbers, and each character is 2 numbers, so 256/2=128

## 1.2 - the checks

there are 2 checks that are preformed when you send a message:

check 1: Size limit
as explained in section 1.1, cloud variables can only hold certain amounts of data, this check is mainly to tell the user that their message did not get sent because it was too large.

check 2: illegal characters
as stated in 1.1, conversion uses the CHAR_KEY, which only holds 89 characters (not all of them are filled in), to combat this, this check looks at every character and sees if it can find them in the CHAR_KEY. if it cant, it flags it and doesn't send the message.

## 1.3 - the other side

when cloudmessanger changes, the code sets off a flag, grabs cloudmessanger and cloudlastuser, and joins them together in the correct order, and then pushes it to the messages list for the user to see.

# Section 2 -
