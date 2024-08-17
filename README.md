# -Multithreaded-end-to-end-encrypted-cryptography-based-real-time-chat.

Multithreaded-End-to-End-Encrypted-Cryptography-Based-Real-Time-Chat
This is an encrypted chat application to make 2 clients offline chatting possible via LAN or Wifi hotspot, thought a connection with a system that is made as a server. The server is unable to decypher the chat and texts among the 2 clients. It is developed by the use of Socket Programming in Python and the encryption is done using RSA Algorithm.

Features
Chatting
Encryption
Secure
Requirments
Python 3 - version 3.6.5

Modules :
socket - Low-level networking interface
threading - Higher-level threading interface
tkinter - Python interface to the Tk GUI toolkit
random - Generate pseudo-random numbers
sys - System-specific parameters and functions
time - Time access and conversions
Instructions
Clone or download the repo: https://github.com/ronaessi-28/Entice
Navigate to the folder Entice
Run the server script Server.py on a system to be made a server that is in connection with the 2 clients
Run the first client script client_1.py on another system
Put the IP of the server that is shown on server console in client_1.py
Put the Port of the server, that is fixed in the server script to 42000
Finally enter your name, e.g.-JOHN
Then run the second client script client_2.py on different system
Put the IP and port of the server in client_2.py and enter your name e.g.-ADAM
Finally, connection is established now!!

You can chat with your friend with with one client as you and another client as your friend. And without server interviewing your chats!! Server script will show the encrypted messages shared among the 2 clients.

Screenshots
Server Sript :


Client_1 Script : Zephyr


Client_2 Script : Klaus


Server after few conversation :


Socket Programming
Socket programming is a way of connecting two nodes on a network to communicate with each other. One socket(node) listens on a particular port at an IP, while other socket reaches out to the other to form a connection. Server forms the listener socket while client reaches out to the server. They are the real backbones behind web browsing. In simpler terms there is a server and a client.

The code for creating a server socket in sockect programming used in this project is given below:

     HOST = gethostbyname(gethostname())     # get host IP
     PORT = 42000
     BUFFER_SIZE = 1024   # buffer size of receiver
     ADDRESS = (HOST, PORT)  # servers socket address

     SERVER = socket(AF_INET, SOCK_STREAM)   # create socket object
     SERVER.bind(ADDRESS)    # bind socket IP and port no.

     SERVER.listen(2)
     print('Server IP: ', HOST)
     print("Waiting for connection...")
     accept_incoming_connections()
     accept_incoming_connections()
The code for connecting a client socket with server socket in sockect programming used in this project is given below:

    HOST = input('Enter host: ')
    PORT = int(input('Enter port: '))
    NAME = input('Enter your name: ')
    BUFFER_SIZE = 1024
    ADDRESS = (HOST, PORT)

    CLIENT = socket(AF_INET, SOCK_STREAM)    # client socket object
    CLIENT.connect(ADDRESS) # to connect to the server socket address
RSA (Rivest–Shamir–Adleman)
RSA (Rivest–Shamir–Adleman) is one of the first public-key cryptosystems and is widely used for secure data transmission. In such a cryptosystem, the encryption key is public and it is different from the decryption key which is kept secret (private). In RSA, this asymmetry is based on the practical difficulty of the factorization of the product of two large prime numbers, the "factoring problem". The acronym RSA is made of the initial letters of the surnames of Ron Rivest, Adi Shamir, and Leonard Adleman, who first publicly described the algorithm in 1978. Clifford Cocks, an English mathematician working for the British intelligence agency Government Communications Headquarters (GCHQ), had developed an equivalent system in 1973, but this was not declassified until 1997.

A key generation function code used in this project is given below:

    def key_generator():
    
        p, q = primes.choose_distinct_primes()
        n = p * q
        phi = (p-1) * (q-1)  # Euler's function (totient)
        e = choice(coprimes(phi))
        d = modinv(e, phi)
        
        public_key = [e, n]
        private_key = [d, n]
        return [public_key, private_key]
