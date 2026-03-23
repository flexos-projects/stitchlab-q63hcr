---
id: "home-screen-farmer-matching"
title: "Home Screen Farmer Matching (StitchLab)"
type: "feature"
status: "draft"
priority: "P1"
description: "Implement a Tinder-like swipe interface on the home screen for farmers to discover, like, dislike, and favorite other farmer profiles for potential matching."
tags: ["home screen", "matching", "farmers", "swipe", "profile", "discovery"]
createdAt: "2026-03-23"
updatedAt: "2026-03-23"
---

# Home Screen Farmer Matching

## Overview
This feature introduces a core discovery and matching mechanism for farmers within the StitchLab application. Mimicking popular dating app interfaces, the home screen will display a stack of nearby farmer profiles. Users can intuitively interact with these profiles by swiping left to dislike, swiping right to like, or tapping to view a more detailed profile. A 'favorite' option will also be available for users to bookmark promising profiles. The ultimate goal is to facilitate connections between farmers based on mutual interest, enabling future collaboration, mentorship, or community building.

## User Stories

*   **As a farmer**, I want to see profiles of other farmers near my location, so I can discover potential connections.
*   **As a farmer**, I want to be able to swipe right on a profile, so I can indicate my interest (like).
*   **As a farmer**, I want to be able to swipe left on a profile, so I can dismiss profiles I'm not interested in (dislike).
*   **As a farmer**, I want to be able to tap on a profile card, so I can view more detailed information before deciding to like or dislike.
*   **As a farmer**, I want to be able to add a profile to my 'favorites' list, so I can easily revisit profiles I find particularly interesting, even if I haven't matched yet.
*   **As a farmer**, I want to receive a notification when another farmer I liked also likes my profile, so I know a mutual match has occurred.
*   **As a farmer**, I want my profile to be discoverable by other farmers within a specified radius, so I can receive likes and matches.
*   **As a farmer**, I want to be able to filter the profiles I see (e.g., by farm type, crop interest), so I can find more relevant connections.

## Requirements

<flex_block type="requirements">
### Functional Requirements
*   **FR1**: The home screen shall display a stack of farmer profiles, one at a time.
*   **FR2**: Users shall be able to swipe right on a profile card to 'like' the farmer.
*   **FR3**: Users shall be able to swipe left on a profile card to 'dislike' the farmer.
*   **FR4**: Users shall be able to tap on a profile card to navigate to a detailed profile view.
*   **FR5**: Users shall be able to mark a profile as 'favorite' from the detailed profile view or directly from the swipe interface (e.g., via an icon).
*   **FR6**: The system shall implement a matching algorithm where a 'match' occurs when two farmers mutually 'like' each other's profiles.
*   **FR7**: Upon a match, both matched users shall receive an in-app notification.
*   **FR8**: Profiles displayed shall be based on the user's current or specified location and a configurable radius.
*   **FR9**: Disliked profiles shall not reappear in the user's swipe stack.
*   **FR10**: Liked profiles shall be moved to a 'liked' section and not reappear in the swipe stack unless manually reset by the user.
*   **FR11**: Profile cards shall display essential information such as name, primary photo, distance, and a brief bio/farm type.
*   **FR12**: Users shall be able to set and adjust discovery preferences (e.g., distance radius, farm types of interest).
*   **FR13**: A 'No more profiles' state shall be displayed when the user has exhausted all available profiles within their discovery settings.

### Non-Functional Requirements
*   **NFR1**: The swiping interaction shall be smooth and responsive, with minimal lag.
*   **NFR2**: Profile loading shall be optimized to ensure quick transitions between profiles.
*   **NFR3**: The system shall scale to support a large number of concurrent users and profiles.
*   **NFR4**: User location data and profile preferences shall be securely stored and transmitted.
*   **NFR5**: The UI/UX shall be intuitive and engaging, consistent with the StitchLab brand guidelines.
</flex_block>

## Acceptance Criteria

*   Given I am on the home screen,
    When I swipe right on a profile card,
    Then the profile is registered as 'liked' by me, the card disappears, and the next profile is displayed.

*   Given I am on the home screen,
    When I swipe left on a profile card,
    Then the profile is registered as 'disliked' by me, the card disappears, and the next profile is displayed.

*   Given I am on the home screen,
    When I tap on a profile card,
    Then I am navigated to the detailed view of that farmer's profile.

*   Given I am viewing a detailed farmer profile,
    When I tap the 'Favorite' icon,
    Then the profile is added to my 'Favorites' list, and the icon state changes to indicate it's favorited.

*   Given Farmer A likes Farmer B's profile,
    And Farmer B likes Farmer A's profile,
    Then both Farmer A and Farmer B receive an in-app notification indicating a 'Match'.

*   Given my location is enabled,
    When I open the home screen,
    Then I see profiles of farmers whose registered locations are within my set discovery radius.

*   Given I have disliked a profile,
    When I continue swiping,
    Then that disliked profile does not reappear in my swipe stack.

*   Given I have liked a profile,
    When I continue swiping,
    Then that liked profile does not reappear in my swipe stack.

*   Given there are no more profiles available within my discovery settings,
    When I try to swipe further,
    Then a message indicating 'No more farmers found in your area' is displayed.

## Edge Cases

*   **No Profiles Available**: What happens when there are no farmers matching the user's discovery criteria (e.g., distance, filters)? The system should display a clear message and suggest adjusting settings.
*   **Geolocation Disabled/Unavailable**: If a user's device geolocation is off or fails, how does the system determine nearby profiles? It should prompt the user to enable location or fallback to a default location.
*   **Incomplete User Profile**: If a farmer's profile lacks essential information (e.g., profile picture, bio), how is it displayed in the swipe stack? Default images or placeholders should be used, and the user prompted to complete their profile.
*   **User Blocks Another User**: If Farmer A blocks Farmer B, Farmer B's profile should not appear in Farmer A's swipe stack, and vice-versa. Any existing match should be dissolved.
*   **Concurrent Likes**: If two farmers like each other simultaneously, the matching algorithm must handle this gracefully and ensure only one match notification is sent to each.
*   **Rapid Swiping**: The UI should handle rapid swiping without crashing or displaying incorrect profile data.
*   **Offline Mode**: How does the feature behave if the user loses internet connection while swiping? Profiles might be cached, but liking/disliking actions should be queued or prevented until connectivity is restored.
*   **Changing Location**: If a user travels and changes their location, the swipe stack should refresh to show profiles in the new vicinity, respecting their discovery settings.
*   **Reporting/Abuse**: A mechanism to report inappropriate profiles should be accessible from the detailed profile view.

## Dependencies

*   **User Profile Service**: Required for retrieving and updating farmer profile data.
*   **Geolocation Service**: Essential for proximity-based profile discovery.
*   **Notification Service**: For delivering match notifications to users.
*   **Search/Filtering Service**: To allow users to refine their profile discovery based on criteria beyond just location.
*   **Image Management Service**: For handling profile pictures and ensuring optimal loading.
*   **Chat/Messaging Feature**: Will be a subsequent dependency for matched users to communicate (out of scope for this spec but highly related).