# Name Game

To run, create a new room with N = 20 (base). If you update the custom_network file, which defines how people are paired, make sure N when creating the room equals the size of the custom_network. 

To do, update the System environment variable with a password. 


### Running multiple sessions (chatGPT how to, check if it works)
How to run two experiments at once with Rooms
1) In settings.py
ROOMS = [
    dict(
        name='room_A',
        display_name='Room A',
        participant_label_file='_rooms/roomA.txt',
    ),
    dict(
        name='room_B',
        display_name='Room B',
        participant_label_file='_rooms/roomB.txt',
    ),
]


Each room is independent.

2) Give each room its own link
http://yourserver:8000/room/room_A
http://yourserver:8000/room/room_B


Participants scanning one QR never mix with the other.

3) What happens live

20 people scan Room A → new session starts

20 people scan Room B → separate session starts

Both games run at the same time

When each finishes, that room resets and waits for the next group
