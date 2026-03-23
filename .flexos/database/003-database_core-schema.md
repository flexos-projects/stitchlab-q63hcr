---
type: spec
subtype: database
title: "Core Database Schema"
description: "Defines the collections and fields for farmer profiles, matching, and messaging."
sequence: 3
status: active
tags: [database, schema, mvp, users, matching, messages]
relatesTo:
  - /.flexos/vision/001-project_vision.md
  - /.flexos/features/002-features_farmer-networking.md
createdAt: "2024-07-30T12:10:00Z"
updatedAt: "2024-07-30T12:10:00Z"
---

# Core Database Schema

This document outlines the main collections (tables) and their respective fields for the 'Tinder for Farmers' application.

## Users Collection
Stores all farmer profile information.
<flex_block type="schema">
{
  "collection": "users",
  "fields": [
    { "name": "id", "type": "string", "required": true, "description": "Unique user identifier" },
    { "name": "name", "type": "string", "required": true, "description": "Farmer's display name" },
    { "name": "email", "type": "string", "required": true, "unique": true, "description": "User's email for authentication" },
    { "name": "passwordHash", "type": "string", "required": true, "description": "Hashed password for security" },
    { "name": "location", "type": "object", "description": "Geospatial data for location-based matching", "properties": [{ "name": "latitude", "type": "number" }, { "name": "longitude", "type": "number" }, { "name": "region", "type": "string" }] },
    { "name": "farmType", "type": "array", "items": { "type": "string" }, "description": "Types of farming (e.g., dairy, crop, livestock)" },
    { "name": "interests", "type": "array", "items": { "type": "string" }, "description": "Hobbies, farming interests, etc." },
    { "name": "photos", "type": "array", "items": { "type": "string" }, "description": "URLs to profile and farm images" },
    { "name": "bio", "type": "string", "description": "About me section" },
    { "name": "lookingFor", "type": "array", "items": { "type": "string" }, "description": "What the farmer is looking for (e.g., romantic, business, friendship)" },
    { "name": "profileVisibility", "type": "string", "enum": ["active", "hidden"], "default": "active", "description": "Controls if profile is discoverable" },
    { "name": "preferredDistance", "type": "number", "description": "Preferred matching distance in km" },
    { "name": "createdAt", "type": "timestamp", "required": true, "description": "Timestamp of user creation" },
    { "name": "updatedAt", "type": "timestamp", "description": "Timestamp of last profile update" }
  ]
}
</flex_block>

## Swipes Collection
Records user's 'like' or 'pass' actions.
<flex_block type="schema">
{
  "collection": "swipes",
  "fields": [
    { "name": "id", "type": "string", "required": true, "description": "Unique swipe identifier" },
    { "name": "swiperId", "type": "string", "required": true, "description": "ID of the user performing the swipe (liker)", "ref": "users" },
    { "name": "swipedId", "type": "string", "required": true, "description": "ID of the user being swiped on (liked)", "ref": "users" },
    { "name": "type", "type": "string", "enum": ["like", "pass"], "required": true, "description": "Type of swipe action" },
    { "name": "createdAt", "type": "timestamp", "required": true, "description": "Timestamp of the swipe action" }
  ]
}
</flex_block>

## Matches Collection
Records mutual 'likes' that result in a match.
<flex_block type="schema">
{
  "collection": "matches",
  "fields": [
    { "name": "id", "type": "string", "required": true, "description": "Unique match identifier" },
    { "name": "user1Id", "type": "string", "required": true, "description": "ID of the first user in the match", "ref": "users" },
    { "name": "user2Id", "type": "string", "required": true, "description": "ID of the second user in the match", "ref": "users" },
    { "name": "createdAt", "type": "timestamp", "required": true, "description": "Timestamp of the match" }
  ]
}
</flex_block>

## Messages Collection
Stores private messages between matched users.
<flex_block type="schema">
{
  "collection": "messages",
  "fields": [
    { "name": "id", "type": "string", "required": true, "description": "Unique message identifier" },
    { "name": "matchId", "type": "string", "required": true, "description": "ID of the match this message belongs to", "ref": "matches" },
    { "name": "senderId", "type": "string", "required": true, "description": "ID of the user who sent the message", "ref": "users" },
    { "name": "content", "type": "string", "required": true, "description": "Content of the message" },
    { "name": "createdAt", "type": "timestamp", "required": true, "description": "Timestamp when the message was sent" }
  ]
}
</flex_block>
