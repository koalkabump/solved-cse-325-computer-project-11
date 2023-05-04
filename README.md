Download Link: https://assignmentchef.com/product/solved-cse-325-computer-project-11
<br>
<h1>Assignment Overview</h1>

<strong> </strong>

This assignment focuses on network programming with sockets, and is the first milestone in a larger project. You will design and implement the program described below.




It is worth 20 points (2% of course grade) and must be completed no later than 11:59 PM on Thursday, 4/16.




<h1>Assignment Deliverables</h1>




The deliverables for this assignment are the following files:




<strong>proj11.client.makefile</strong> – the makefile which produces  <strong>proj11.client proj11.client.c</strong> – the source code file for your client




Be sure to use the specified file names and to submit your files for grading via the CSE Handin system before the project deadline.




<h1>Assignment Specifications</h1>




The following executable file is available on the CSE system:




<strong>/user/cse325/Projects/project11.server </strong>




When executed, that server process will interact with a client process to provide a rudimentary mechanism for copying a text file from one system to another.




<ol>

 <li>The server will create a socket, bind it to a port, and listen for connection requests on that port. It will display the host name and port number on the standard output stream.  For example:</li>

</ol>




<strong>arctic.cse.msu.edu 55000 </strong>




The server process will then accept a connection request from the client process and wait for the client to send it a file name.




If the server is unable to open the specified file name as an input file, it will send the seven-character message FAILURE to the client and terminate execution.  Otherwise, the server will send the seven-character message SUCCESS to the client and wait for the client to respond.




If the client responds with the seven-character message PROCEED, the server will send the contents of the input file to the client and then terminate execution.




<ol start="2">

 <li>The client process will accept three command-line arguments: the host name and port number being used by the server process, as well as the name of the desired file.  For example:</li>

</ol>




<strong>proj11.client arctic.cse.msu.edu 55000 /user/cse325/Examples/example01 </strong>




The client process will connect to the server process, send it the name of the desired file, and wait for a response from the server.




If the server responds with the seven-character message SUCCESS, the client will respond with the seven-character message PROCEED and wait for the server to send it the contents of the desired file.  The client will display the contents of the desired file on the standard output stream and then terminate execution.




<ol start="3">

 <li>The client process will perform appropriate error-handling.</li>

</ol>




<h1>Assignment Notes</h1>




<ol>

 <li>As stated above, your source code file will be named “proj11.client.c”; that source code file may contain C or C++ statements.</li>

</ol>




<ol start="2">

 <li>You must use “g++” to translate your source code file in the CSE Linux environment.</li>

</ol>




<ol start="3">

 <li>You must execute the instructor-supplied server process before executing your client process. You should open two terminal windows:  one to execute the server process and one to execute the client process.</li>

</ol>




Be sure to test you solution in several different ways.  For example, execute your server process and your client process on the same CSE server, then execute the two processes on two different CSE servers.




<ol start="4">

 <li>If instructor-supplied server process is executed with “-debug” as a command-line argument, the server will display additional information which might be useful for debugging.</li>

</ol>




<ol start="5">

 <li>Your client process is required to use the system calls “send()” and “recv()” to exchange messages with the server process.</li>

</ol>




<ol start="6">

 <li>Your client process is required to use the system call “write()” to display the contents of the desired file on the standard output stream.</li>

</ol>




<ol start="7">

 <li>If your client process produces any additional output (beyond the contents of the desired file), it must send that additional output to the standard error stream.</li>

</ol>




<ol start="8">

 <li>Your client process must use a buffer of size 128 bytes to receive the contents of the desired file. For most files, it will require multiple calls to “recv()” and “write()” to process the entire file.</li>

</ol>




<ol start="9">

 <li>Information about some of the system calls you will use is available in section 2 of the “man” utility:</li>

</ol>




<strong>man 2 socket man 2 connect man 2 send man 2 recv man 2 write </strong>


