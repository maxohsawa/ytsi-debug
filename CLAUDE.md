# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is a Youth Team Strength Index (YTSI) web application - a single-page form for evaluating youth soccer teams (U6-U20). The form collects team information and performance metrics, then submits the data to a Google Apps Script endpoint for processing.

## Project Structure

The project consists of a single HTML file:
- `index.html` - Contains the complete form application with embedded CSS and JavaScript

## Key Components

### External Dependencies
- **Bulma CSS Framework** (v0.9.4) - Loaded from CDN for styling
- **jQuery** (v3.6.0) - Loaded from CDN for DOM manipulation

### Form Submission
- Data is submitted to a Google Apps Script endpoint
- Endpoint URL: `https://script.google.com/macros/s/AKfycbxAb2BpjJQ4CieC57judR-R543wyJGV8RbWoiawfXuOKKNhRx7GVyj-JxLB8fWnxT0/exec`
- Method: POST with `text/plain;charset=utf-8` content type
- Form data is serialized as key=value pairs joined with &

### Dynamic Elements
- Country dropdown populated from a hardcoded list of 200+ countries
- Team year dropdown dynamically generated for U6-U20 (current year - 6 to current year - 20)

## Common Development Tasks

Since this is a static HTML file with no build process:
- **View the application**: Open `index.html` directly in a web browser
- **Test form submission**: Fill out the form and submit (requires active internet connection)
- **Modify styling**: Edit the embedded CSS in the `<style>` tag or update Bulma classes
- **Update form fields**: Modify the HTML form elements directly
- **Change submission logic**: Edit the JavaScript in the submit event handler (lines 750-812)

## Important Notes

- The form requires all fields except "Team State" to be filled out
- Form submission displays status messages and alerts on success
- The Google Apps Script endpoint is external and not part of this repository
- No local server or build process is required - this is a client-side only application