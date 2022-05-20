--------------------- disC ----------------------

disC is a discord bot library that is designed to
allow for a developer more used to writing low-l-
evel software to write their discord bot. the pr-
oject is designed to be as efficient using small 
dependencies and providing the least overhead. t-
he project will include a full implementation of 
discord's api, both over the websocket and over 
the http api. disC is designed to provide the le-
ast assistance to developers, so developers would
have to implement their own cache, and interpret 
the output from http apis themselves (we will gi-
ve then a json library though, so it wont be as 
bad), so that they have total control of their b-
ot without our interference. this is by design. 

in advance, i thank you for checking out this pr-
oject.

------------------ building ---------------------

disC uses the cmake build system. first, run `cm-
ake .`, then run `make`. this will output a stat-
ic library, which you can then add to your build 
system for your bot.

---------------- getting started ----------------

disC does not hijack the main function. to get s-
tarted, you can copy this example

> #include <stdio.h>
> #include "disC.h"
> 
> void ready_event(cJSON *eventData) {
>     cJSON *userData = cJSON_GetObjectItemCaseSensitive(eventData, "user");
>     char *username = cJSON_GetObjectItemCaseSensitive(userData, "username");
> 
>     printf("%s now up & running!\n");
>     
>     return;
> }
>
> int main(void){
>     Client *client = disC_createClient();
>     // create clientopts (exempted)
>     disC_registerEvent(client->eventMan, EVENT_READY, &ready_event);
> 
>     disC_start(client);
>     // code after disC_start will NOT run
>     // disC_start runs exit() at the end
> }

-------------------- issues? --------------------

the github repository (turret-dev/disC) has issu-
es enabled.

if the issue is a potential security vulnerabili-
ty, then only disclose it to turret@duck.com

issues must have code linked and a debugger outp-
ut, or they will be disregarded as "not enough i-
nformation".

------------------ contributing -----------------

contributors must sign off theirs commits, certi-
fying to the terms as stated on the Developer Ce-
rtificate of Origin, which is available at 
https://developercertificate.org .

contributors should also conform to a code style 
similar to that of the rest of the code.

-------------------------------------------------
