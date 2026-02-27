+++
title = "More Than the Ticket: A Day in the Life of an MSP Tech"
date = "2026-02-25T14:13:23-05:00"
type = "posts"
#dateFormat = "2006-01-02" # This value can be configured for per-post date formatting
author = ""
authorTwitter = "" #do not include @
cover = ""
tags = ["MSP", "Tickets"]
keywords = ["", ""]
description = ""
showFullContent = false
readingTime = false
hideComments = true
+++

### More Than the Ticket: A Day in the Life of an MSP Tech

A day in the life of an MSP tech is way more than just reading tickets and closing them out. Most of the time, the real work is translating what the client thinks is happening into what’s actually happening—then proving it with facts.

Because here’s the thing: what’s written in a ticket is only the issue from the user’s perspective, with the details they know to include. And that means the ticket is often a symptom… not the diagnosis.

The Ticket: “I can’t change my password”

A ticket comes in and it’s short:

“I’m having a problem being able to change my own password.”

That’s it. No error message. No screenshot. No mention of where they’re trying to change it. No clue if this is an email password, a Windows password, a VPN password, or something else entirely.

So the first step isn’t “start clicking around.” The first step is a follow-up call. Because the fastest way to solve the problem is to make sure you’re solving the right problem.

The Real Problem: “I need to reset my computer password”

After talking with the user, it becomes clear: they’re trying to change the password for their Windows login—an Active Directory account.

Now we’ve got direction. This isn’t a random settings issue or a Microsoft 365 password reset. This is domain authentication, policy, permissions, and potentially GPO.

First Fix: Check Active Directory settings

Next step: connect to the domain controller and review the user account settings in Active Directory Users and Computers.

And sure enough—there it is:
	•	“User cannot change password” is checked.

That setting alone can stop someone from being able to update their password the normal way. So you uncheck it, apply the change, and follow up with the user expecting a quick win.

Except… it still doesn’t work.

The MSP Reality: One symptom can have multiple causes

This is where MSP work gets fun (and sometimes annoying).

You did the obvious fix. You corrected the account permission. But the issue continues—meaning the ticket wasn’t lying… it was incomplete.

So now it’s time to widen the scope:
	•	Is there a policy blocking it?
	•	Is there a registry setting overriding it?
	•	Is a security baseline enforcing something?
	•	Is the Ctrl+Alt+Del “Change a password” option missing?
	•	Is this machine configured differently than the rest?

The Actual Fix: A registry setting was blocking password changes

After digging in and doing some research, you discover something important:

Even though Active Directory now allows the password change, the computer itself has a registry value set that prevents users from changing passwords.

In other words, AD says “yes,” but Windows says “no.”

So you run the command needed to correct that registry setting, re-test with the user, and this time—the option is back and the password change works.

The takeaway: MSP work is detective work

This ticket wasn’t solved by blindly following steps. It was solved by understanding the bigger picture:
	•	The ticket text was limited
	•	The user’s description was valid—but incomplete
	•	Active Directory was part of the issue
	•	The workstation configuration was the other part
	•	The fix required both account-side and device-side troubleshooting

That’s the difference between “working tickets” and actually supporting people.

Because being an MSP tech isn’t about reading what’s in front of you—it’s about understanding what’s missing, asking the right questions, and troubleshooting from every angle until the problem is truly fixed.