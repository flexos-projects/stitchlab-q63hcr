---
id: login-page
title: "Login Page"
type: page
subtype: route
status: active
sequence: 11
description: "User login page with email/password and social login options."
tags: [pages, auth, login]
relatesTo: [docs/003-pages.md, flows/001-user-authentication.md]
createdAt: "2024-07-30T12:20:00Z"
updatedAt: "2024-07-30T12:20:00Z"
---

<flex_blocks_section>

<flex_block type="instructions" id="blk-001" name="login-page-context">
This page handles user authentication, allowing existing farmers to log in to the platform.
It should support both email/password and social login options.
</flex_block>

<flex_block type="sitemap" id="blk-002" name="login-page-route">
{
  "route": "/login",
  "name": "Login",
  "component": "LoginPage",
  "authRequired": false
}
</flex_block>

</flex_blocks_section>

# Login Page

Users can access this page to log in to their farmer profile.

## Key Components
- Email and password input fields
- "Forgot Password" link
- Social login buttons (e.g., Google, Apple)
- Link to registration page for new users
