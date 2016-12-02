# Chat-on
Chat server using Unix based BSD sockets

To simulate the chat-server for Unix/Linux environment. The simulation is implemented using Unix domain sockets. User-clients
who wish to chat are required to login to the chat-server. They can send messages to any other client in the lobby. Though a user-client can chat with multiple users, (s)he is not allowed to multicast or broadcast.

Functional requirements:
Client Functional Requirements:
1.User can either login with existing username and password or can register with new ones. The
commands for the same are
register <username> <password>
login <username> <password>

2.Upon successful login, user can see names of all logged-in users in the lobby. User can sendmessages to other active users using the command
send <receiver_username> <message>

3.Client can logout. The command for the same is
logout

4.Client can demand the names of online users using the command
lobbystatus

5.Users get proper messages for every new user coming online or for every existing user logging out.
Every time the lobby gets updated, user automatically gets the new lobby status without having to explicitly demand it.

Server Functional Requirements:
1.Server authenticates every user.

2.Server manages registrations of new users.

3.Server maintains the lobby details at every time.

4.Server can broadcast messages. These messages will be broadcasted to every online client-users. The command for broadcasting is
broadcast <message>

5.Server can send message to any specific client using the command
send <receiver_username> <message>

6.Server can kick any user from the lobby using the command
kick <username> <optional-field-reason_for_the_kick>

7.All other users will get proper message informing them about the kick.
Server can ban any user. This user will be kicked from the lobby (if online) and won’t be able to
log in further using same username and password. Also any client can get unbanned too. The commands to ban and unban are
ban <username> <optional-field-reason_for_the_ban>
unban <username>

8.All other users will get proper message informing them about the ban/unban.

9.Server also maintains several logs for various activities using proper timestamps.

10.Server can terminate using the command
logout
