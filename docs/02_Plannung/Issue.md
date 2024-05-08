Microservice Info
Open
 Issue
created
2 days ago
by
Boris Langer
Story

As a user I want to be able to see how the implementation of a room is linked to (advanced) micro-service concepts. Therefore the creator of the room should be able to enter a text that describes the above linkage.

Acceptance criteria

In the add/edit-room page there must be a text field where the ms-context can be described
Enter any room in a game, press the ms button. Text shall be displayed
UI

The text shall be displayed during a room-visit in a game in the browser. It shall be displayed upon a button press on the page play-game in the frontend.

Data persistence

A corresponding field (ms_context) in the class Room has already been defined in the file room.py

Effort

T-Shirt Size: 5

DoR -> Definition of Ready

Story defined
Acceptance criteria defined
Effort estimated  - Scrum Poker -> In Story Points -> srumpokeronline.org
Team assigned and agrees on story description
DoD  -> Definition of Done

Tests defined (backend)
Tests pass during CI test task
Merge request created
Demo with product owner planned