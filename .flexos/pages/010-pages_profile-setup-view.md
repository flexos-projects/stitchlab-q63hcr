---
type: spec
subtype: pages
title: "Profile Setup/View Page"
description: "Allows farmers to create, view, and edit their personal and farm profiles."
sequence: 10
status: active
tags: [pages, profile, onboarding, user-management]
relatesTo:
  - /.flexos/vision/001-project_vision.md
  - /.flexos/features/002-features_farmer-networking.md
  - /.flexos/database/003-database_core-schema.md
createdAt: "2024-07-30T12:15:00Z"
updatedAt: "2024-07-30T12:15:00Z"
---

# Profile Setup/View Page

This page serves as the central hub for a farmer's identity within the application. It allows new users to set up their profiles and existing users to view and update their information.

## Key Sections & Elements:

### 1. Profile Header
- **Avatar/Profile Picture**: Prominently displayed.
- **Name & Location**: Farmer's name, region/state.
- **Farm Type Tags**: Visual indicators of farming specializations (e.g., #Dairy, #OrganicCrops).

### 2. Image Gallery
- **Farm & Personal Photos**: A scrollable gallery showcasing farm life and the farmer themselves.
- **Upload Functionality**: (For setup/edit mode) Users can add, reorder, and delete photos.

### 3. About Me / Bio Section
- **Bio Textarea**: A free-form text area for a detailed description.
- **Interests List**: Tags or selections for farming interests, hobbies, etc.
- **Looking For**: Clearly states what the farmer is seeking (e.g., "Looking for: Romantic Partner, Business Collaboration").

### 4. Edit Profile / Save Actions
- **Edit Button**: (For view mode) Navigates to edit mode.
- **Input Fields**: (For setup/edit mode) Editable fields for name, location, farm type, interests, etc., pre-populated with existing data.
- **Save/Cancel Buttons**: (For setup/edit mode) To commit changes or discard them.

### 5. Settings / Privacy Options
- **Profile Visibility Toggle**: (Access from profile) To activate or hide the profile from discovery.
- **Preferred Distance Selector**: (Access from profile) To set matching radius.

## User Flow for Profile Setup & Editing:
<flex_block type="flow">
{
  "steps": [
    { "type": "action", "name": "User lands on Profile page (empty if new, populated if existing)", "actor": "user", "route": "/profile" },
    { "type": "action", "name": "System checks if profile exists", "actor": "system" },
    { "type": "decision", "question": "New user?", "options": [
      "Yes → Show setup fields",
      "No → Show view mode with 'Edit' button"
    ]},
    { "type": "action", "name": "User fills in/edits profile details (name, farm type, bio, photos, looking for)", "actor": "user" },
    { "type": "action", "name": "User clicks 'Save Profile'", "actor": "user" },
    { "type": "action", "name": "System validates input and saves to database", "actor": "system" },
    { "type": "decision", "question": "Save successful?", "options": [
      "Yes → Show confirmation and switch to view mode",
      "No → Show error messages for invalid fields"
    ]},
    { "type": "action", "name": "User views their updated profile", "actor": "user" }
  ]
}
</flex_block>
