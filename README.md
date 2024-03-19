# Test Scenarios/Cases for Card Game API
## 1. Load and Verify Contents from Home Page
+ #### _Purpose_: Verify if the response code is 200 OK and check if the body contains the required content.
+ #### _Method_: GET
+ #### _Endpoint_: Home Page
+ #### _Validation Steps_: a) Assert response status code b) Assert the content data from the response.

## 2. Create a New Unshuffled Deck
+ #### _Purpose_: Construct a new unshuffled deck.
+	#### _Method_: POST
+	#### _Endpoint_: https://deckofcardsapi.com/api/deck/new/
+	#### _Validation Steps_: a) Assert response code b) Assert required fields are populated c) Validate the 'shuffled' property d) Validate datatypes for the fields returned in response.

## 3. Shuffle an Existing Deck
+ #### _Purpose_: Shuffle an existing deck based on the deck_id provided.
+	#### _Method_: GET (Considered as a GET operation since it's merely rearranging the deck)
+	#### _Endpoint_: https://deckofcardsapi.com/api/deck/{deck_id}/shuffle/
+	#### _Validation Steps_: a) Assert response code b) Assert required fields are populated c) Validate the 'shuffled' property d) Validate datatypes for the fields returned in response.

## 4. Draw 6 Cards (2 Players x 3 Times)
+ #### _Purpose_: Draw 6 cards from a deck.
+ #### _Method_: GET
+ #### _Endpoint_: https://deckofcardsapi.com/api/deck/{deck_id}/draw/?count=6
+ #### _Query Parameter_: count=6 (Defines the number of cards to draw)
+ #### _Business logic_:
  + Distribute the drawn cards alternatively to each player.
  + Calculate the sum of card values for each player using the JavaScript function calculateSum.
  + Identify players with a Blackjack based on the calculated sum:
  + Append numbers, followed by J, Q, K.
  + Consider Ace as 1 if the existing sum is > 21; otherwise, Ace is 11.
+ #### _Validation Steps_: a) If the sum of cards is 21, the player is considered to have a Blackjack.



