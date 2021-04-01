# FreePBX Missed Call Email Notification
A small Asterisk dialplan that works with FreePBX to send an email when you have a missed call.

## Install and setup
1. Add the dialplan to extensions_custom.conf
2. Change the from email address (look for `sender@domain.com` in the dialplan and change that).
3. Change the default to email (look for `general@domain.com` in the dialplan and change that)
4. DONE!!! Reload config and test.

## Features
* Sends an email to the address configured under the voicemail tab on internal, external and queue missed calls.
**Note:** If voicemail is disbaled, it will not work!
* If the call comes through a Queue, you will see in the email which queue the call came from.
* If the extension is offline, you will see that in the email as well.
* You can set this feature for each extension individually, or exclude certian extensions from the GUI using the AccountCode field under the advanced tab.

### Known Limitations/Issues:
* Only works with chan_sip and chan_pjsip extensions.

* The predial hook is not being called when a PJSIP extension is offline resulting this feature not to work.

* Does not work well with Ring Groups - We are removing the hangup handler now if a call comes through a ring group.

* Virtual extensions are NOT included.

* Paging was not tested yet, it may or may not cause issues.


#### Tested with:
- [ ] FreePBX 13 Asterisk 13
- [ ] FreePBX 13 Asterisk 16
- [X] FreePBX 14 Asterisk 13
- [X] FreePBX 14 Asterisk 16
- [ ] FreePBX 14 Asterisk 18
- [ ] FreePBX 15 Asterisk 16
- [ ] FreePBX 15 Asterisk 18
