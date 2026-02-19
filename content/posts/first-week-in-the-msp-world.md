+++
title = "Authentication Context in Microsoft 365"
date = "2026-02-17T21:13:23-05:00"
#dateFormat = "2006-01-02" # This value can be configured for per-post date formatting
author = ""
authorTwitter = "" #do not include @
cover = ""
tags = ["MicrosoftEntra", "Entra"]
keywords = ["", ""]
description = ""
showFullContent = false
readingTime = false
hideComments = true
+++

### Conditional Access Policy 

All Users – Auth Context Sensitive Data – Require Compliant Device  
#### Users  
	Include: All Users  
	Exclude: Break glass account
#### Target Resources 
	Drop down to Authentication Context 
		Check the box next to the Authentication context policy that was created. 
#### Grant
	Grant Access
		Require Authentication Strength
			Select the strength 
		Select Require device to be marked as compliant



