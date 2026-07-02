this room was pretty simple honestly.

i booted up the machine and the attackbox and i got straight to work.

firstly i scanned the machine's open ports using nmap:

<img width="1920" height="1080" alt="Screenshot_2026-07-02_17-00-20" src="https://github.com/user-attachments/assets/333fab3b-4653-4f8f-ad13-2fa6a454f479" />

as you can see, the https port is open, so my first thought was to search for the ip on a browser, which yielded this:

<img width="1920" height="1080" alt="Screenshot_2026-07-02_17-12-11" src="https://github.com/user-attachments/assets/3bbe5972-37bf-4ebb-b706-79a91f6128b7" />

i ignored the false postitve and continued, which gave me this page:

<img width="1920" height="1080" alt="Screenshot_2026-07-02_17-14-31" src="https://github.com/user-attachments/assets/58d833f4-48e1-47e5-900f-fabdb7a3594b" />

ok i guess. anyways i inspected the page, and found this:

<img width="1920" height="1080" alt="Screenshot_2026-07-02_17-16-38" src="https://github.com/user-attachments/assets/54b3ff65-8b0e-411c-8a14-32b7512474ca" />

unfortunately, i didn't know what to do with this information. i used burp suite to search for related pages, clicked around the page for any hidden links, everything i could do i did. i think i missed something or i dont have the knowledge to currently captilize on this maybe. ill try to search more on this specific part. (this may also be a red herring but i highly doubt it; i think im just too much of a noob to know what to do with this info).

finding myself stuck i searched for another way in.

then i remembered what room i was in (lol). i checked the supported tls versions:

<img width="1920" height="1080" alt="Screenshot_2026-07-02_19-18-04" src="https://github.com/user-attachments/assets/a2ab176a-6356-4ab1-b7d4-94e5aacc3f83" />

yup, tls v1.0 is supported, meaning we can use heartbleed.

i booted up metasploit and got straight to work:

<img width="1920" height="1080" alt="Screenshot_2026-07-02_19-55-56" src="https://github.com/user-attachments/assets/f8e88be9-6f81-4616-8200-9e934571f36d" />

bingo! now all we need is to get the files' contents and pipeline them through grep for THM:

<img width="1920" height="1080" alt="Screenshot_2026-07-02_20-05-06" src="https://github.com/user-attachments/assets/5f6d6247-3bc9-4334-bddc-537d6c0cc136" />
(ignore the dumb mistakes i made trying to make the bin file into a .txt lol)

tada! we've found the flag! 

i really like this room it was pretty easy but still fun.

thank you for your time!














