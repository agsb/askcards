# askcards

-- this file is a stub -- still

Play Decision Tables from simple  (question/yes/no/response) cards

Cards define the structure of sequence of questions with yes or no responses, only.
Each card have a identification, by now, a long integer (4 bytes), maybe at future a uuid.
Each card have a counter of how many cards points to it.
Each card have some flags for control.

Conditions:

Each question card must point to a Yes card (okey) and to a No card (nyet).

A response card do have a NULL (zero) in okey and nyet;

## Card definition

A single struct holds a record card, defined by

    index,  a number of this card
    okey, the card to go if answer is yes
    nyet, the card to go if answer is no
    question/response, the question or response
    counter,  a counter of links to this card
    flags,  some flags for this card

for tests a record card is 128 bytes, then question is a asciiz string of 111 characters;

index, okey, nyet are long integers, as a linked list, count and flag are integers, and question is char[];

first 8 cards, 0 to 7 are reserved for indexes and status


** using libc definitions
