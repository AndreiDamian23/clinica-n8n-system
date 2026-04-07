# clinica-n8n-system
AI automation system for clinic: lead follow-up, booking and reactivation using n8n

# AI Appointment Management & Recovery System

## Overview
This system automates the full appointment lifecycle for clinics, including booking, confirmation, no-show tracking, and reactivation.

It uses two AI voice agents and multiple fallback mechanisms to ensure maximum appointment attendance and recovery.

---

## Core Components

### 1. Booking Voice Agent (Agent #1)
- Handles incoming and outgoing calls
- Can:
  - Book appointments
  - Reschedule appointments
  - Cancel appointments

---

### 2. SMS Confirmation System
- Sends automatic SMS reminders 24 hours before appointment
- Waits for client confirmation

---

### 3. Confirmation Voice Agent (Agent #2)
- Triggered if client does not respond to SMS within 30 minutes
- Calls the client to confirm the appointment
- Can also handle incoming callbacks from clients

---

### 4. No-Show Tracking System
- If client:
  - Does not respond to SMS
  - Does not answer calls
  - Does not call back

→ Contact is automatically moved to "NO SHOW TRACKING" sheet at end of day

---

### 5. Follow-Up & Recovery System
- All contacts in NO SHOW TRACKING are recontacted
- Goal: recover lost appointments and reschedule

---

## System Logic Flow

1. Appointment is created
2. 24h before → SMS sent
3. If no response in 30 min → Confirmation Agent calls
4. If still no response → mark as potential no-show
5. End of day → move to NO SHOW TRACKING
6. Follow-up system attempts rebooking

---

## Tech Stack
- n8n (workflow automation)
- AI Voice Agents (via external API)
- Google Sheets / CRM
- SMS API

---

## Purpose
Reduce no-shows, automate confirmations, and recover lost revenue from unresponsive clients.


