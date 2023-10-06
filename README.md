# POST-Codes suck. Really!


Ignoring the price they add to a motherboard, what even is it that they show?

Usually it is simply a changing two digit hexadecimal number that arbitrarily changes throughout the Poweron and boot process of a modern computer.

Supposedly those numbers mean something usefull so that once there is an issue, it can be clearly identified and then resolved.

In practice that is hardly the case.

Looking at any manual for an affected motherboard should yield a list of corresponding meanings, descriptions or even recommendations on what to do now. 

Most of those sadly turn out to be nonesense in practice for multiple reasons.

## Presentation 

7 segment LED displays are not the only display of those codes.
Seperate Displays be they OLED or LCD are becoming a thing on higher end motherboards.
Most notably though, POST-Codes have always been shown in a corner of main screen once there was signal from the system.
This does not help at all with issues preventing the system from reaching that point.
Server systems offer two solutions to that problem, early video output where there is gona be a picture on the screen from close to the moment that you turn the system on.
Supermicro and ASRack, being decently enough in my experience where as Giglebyte completely fails in some cases.
And remote management interfaces that offer diagnostic capabilities, sometimes including "postcode snooping" or even a log or history of post-codes.

The mayor problem with all of those in combination is that they add inconsistency.
On screen could be one code where as your board shows another on the OLED and even worse, another one on the 7 segments.
Which of those now is the one you believe?

From expreince, the 7 segment displays are what i trust.

## OEMs and Platforms

The mayor difference of course exists between AMD and Intel platforms but even here there are differences between the OEMs based on the OEM provider they went with for their UEFI implementation.
AMI (American Mega Trends) being one of the more prevalent ones nowadays.

This still means that general knowledge from experience can't be applied to systems from other platforms or OEMs.

## Where do postcodes even come from

There are usually two types of codes. 
Checkpoint codes that signify that a certain step in the PowerOnSequence has been passed.
And Error codes for catastrophic cases where there is nothing else left to do.

Source of those numbers is UEFI / BIOS Code running on the CPU that simply broadcasts those codes to the rest of the platform.

There usually is no distinction between the two and mayhaps numbers have benn reused now having multiple different meanings.

With AMD the situations is even worse because there is not one source but two.
In addition to the X86 Cores, the ARM CPU inside called PSP (Platform Secure Processor) does also broadcast codes.
On the PSP itself there again are ERROR Codes, ABL (Agesa Boot Loader) progress (checkpoint) and Error codes.
Luckily those are different 8 digit hexadecimal numbers.

But since we only get to see the least significant 2 digits, there is no way for us to differentiate.

All of that makes the pile of meanings grow to more then 4 making this more of a guessing game then anything else.

## Ar they even correct?

If you have found a probable meaning for a code shown on your non functioning system, likely hood of it actually telling you what the issue is, is very slim.

The best and only example i can give is the Error code 53 on most AMI Intel platforms.
It informs that there is no Memory present, be that because there is none, or because it could not find any.
The later usually occuring on some platforms when Memory was only put into the wrong slots.
But a plethora of issues can cause failures to detect the memory or other codes to be shown 
