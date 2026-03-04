# Authentication System Guide

## Overview
A complete authentication system has been implemented using localStorage for data persistence.

## Features

### 1. Sign Up (`/signup`)
- Users can create a new account with:
  - Full Name
  - Email Address
  - Password (minimum 6 characters)
  - Password Confirmation
- Validates that passwords match
- Checks for duplicate email addresses
- Automatically signs in after successful registration

### 2. Sign In (`/signin`)
- Users can log in with:
  - Email Address
  - Password
- Validates credentials against stored users
- Shows error messages for invalid credentials

### 3. User Profile (`/profile`)
- Protected route (requires authentication)
- Displays user information:
  - Profile avatar (first letter of name)
  - Full name
  - Email address
  - Member since date
- Redirects to sign-in if not authenticated

### 4. Navigation Bar
- Shows "Sign in" button when logged out
- Shows user name with dropdown menu when logged in
- Dropdown includes:
  - Profile link
  - Sign out button

## How It Works

### Data Storage
- User accounts are stored in `localStorage` under the key `users`
- Current session is stored under the key `currentUser`
- Data persists across browser sessions

### Authentication Flow
1. User signs up → Account created → Auto sign-in → Redirect to home
2. User signs in → Credentials validated → Session created → Redirect to home
3. User signs out → Session cleared → Redirect to home

## Usage

### Test the System
1. Click "Sign in" button in the navbar
2. Click "Sign up" to create a new account
3. Fill in the form and submit
4. You'll be automatically signed in and redirected to home
5. Click your name in the navbar to see the dropdown
6. Visit your profile or sign out

### Demo Credentials
Since this uses localStorage, you'll need to create your own account first.

Example:
- Name: John Doe
- Email: john@example.com
- Password: password123

## Security Notes

⚠️ **Important**: This is a demo implementation using localStorage. For production:
- Use a proper backend authentication service
- Never store passwords in plain text
- Implement proper password hashing (bcrypt, argon2)
- Use JWT tokens or session cookies
- Add HTTPS
- Implement rate limiting
- Add email verification
- Add password reset functionality

## Files Created

- `/app/signin/page.tsx` - Sign in page
- `/app/signup/page.tsx` - Sign up page
- `/app/profile/page.tsx` - User profile page
- `/hooks/useAuth.ts` - Authentication hook
- `/components/Navbar.tsx` - Updated with auth state

## Future Enhancements

Consider adding:
- Password strength indicator
- Remember me functionality
- Social login (Google, Facebook)
- Two-factor authentication
- Email verification
- Password reset via email
- User settings page
- Profile picture upload
