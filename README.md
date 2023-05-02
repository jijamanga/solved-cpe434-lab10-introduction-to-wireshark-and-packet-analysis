Download Link: https://assignmentchef.com/product/solved-cpe434-lab10-introduction-to-wireshark-and-packet-analysis
<br>
Wireshark is a packet analyser tool. Apart from being a packet analyser, it is also a network sniffer tool. So it provides the option of capturing packets flowing in and out of a network as well as analyse and troubleshoot with a nice GUI. It allows live capture of packets which means you can capture and save information about the networks packets from a live network in real time.

To run live capture, a user needs sufficient privileges. However, you can analyze the packet-data based on trace files without super user privileges.

<h1>How to run Wireshark on Linux</h1>

Open a terminal (type ​<strong>Ctrl+Alt+t​</strong>). Once you are inside terminal, type ​<strong>wireshark ​</strong>and hit enter. You should see a screen as in following figure.




It should open the GUI as shown in the following figure.




We will download trace files that are available online and then analyze them to extract some information.

In your report, please make sure that you include screenshots of all the steps as you perform them as a proof of your work even if the assignment does not mention explicitly.

<strong>How to run Wireshark on Windows or Mac </strong>

You may go to the following <u>​</u><a href="https://www.wireshark.org/download.html">link </a>to download wireshark for Windows or Mac machines.​                  <strong> </strong>

<h1>How to run Wireshark on WSL2</h1>

Please refer to the course WSL 2 document provided along with the lab module if you wish to run wireshark from WSL2.

<h1>Subtask 1 (Introduction)</h1>

<ol>

 <li>Go to <u>​</u><a href="https://wiki.wireshark.org/SampleCaptures">SampleCaptures</a> <a href="https://wiki.wireshark.org/SampleCaptures">–</a> <a href="https://wiki.wireshark.org/SampleCaptures">The</a> <a href="https://wiki.wireshark.org/SampleCaptures">Wireshark</a> <a href="https://wiki.wireshark.org/SampleCaptures">Wiki</a>.​ This website contains a list of sample trace files that are output of network capturing. let us find a simple unencrypted trace file, load it in wireshark and analyze it.</li>

 <li>Go to <u>​</u><a href="https://wiki.wireshark.org/SampleCaptures#Telnet">number 20</a>​, which should give you telnet packets as the following figure shows.</li>

 <li>Download the first pcap file ​<a href="https://wiki.wireshark.org/SampleCaptures?action=AttachFile&amp;do=get&amp;target=telnet-cooked.pcap"><strong>telnet-cooker.pcap</strong></a></li>

 <li>On the wireshark window, select ​<strong>File-&gt;Open ​</strong>to open a dialog box that lets you choose the pcap file. Navigate and open the pcap file that you downloaded earlier.</li>

 <li>Once you select ​<strong>Open​</strong>, you will see a window something like the following figure.</li>

</ol>

<h2>Assignments</h2>

<ol>

 <li>How many packets are captured in the .pcap file that you loaded?</li>

 <li>List all the communicating parties in the .pcap file? Can you also identify the ports being used by each of them?</li>

 <li>What protocols are used for communication by the communicating parties ? 4. What is the total duration of the communication? (You may want to see the first and last frame)</li>

 <li>What is the frame length and number of the longest frame transferred? Who is the source and destination of that packet?</li>

</ol>

<h1>Subtask 2 (Real Hacking and Stuff)</h1>

Now that you have sniffed someone in a network and got the data that is being tranferred. You also know who is involved in communication. Now we want to see if we can get something of real value for us. May be someone has transferred his/her username and password over the network that we sniffed.

<h2>Assignments</h2>

<ol start="6">

 <li>Select frame number 8. Who is the sender and receiver of this frame?</li>

 <li>On the window that appears below the listing of all the frames (as shown below), expand Internet Protocol Version 4. What is the Time To Live of this frame? What does this mean?</li>

 <li>Select frame 8 again. Right click on it, and select ​<strong>Follow TCP Stream​</strong>. What information can you see? What is the username and password that is transferred?</li>

 <li>Repeat the same procedure in <u>​</u><a href="https://wiki.wireshark.org/SampleCaptures?action=AttachFile&amp;do=get&amp;target=telnet-raw.pcap"><strong>telnet-raw.pcap</strong></a><strong>​</strong>. Find the login information used to verify credentials. (Select frame 8 again)</li>

 <li>What do you think is wrong with these two files that you analyzed? How can you not allow anyone to know your password that you send for authentication?</li>

 <li>Load the file <u>​</u><a href="https://wiki.wireshark.org/SampleCaptures?action=AttachFile&amp;do=get&amp;target=UFTP_v3_transfer.pcapng"><strong>pcapng</strong></a><strong>​</strong>. The protocol used is UFTP. What is UFTP? Can you identify two parties that are involved in file transfer. (Use your intelligent guessing) 12. Write differences between TCP and UDP.</li>

</ol>

<h1>Subtask 3 (Decrypting The Encrypted)</h1>

Let us now work on encrypted protocol.

<ol start="12">

 <li>What is the difference between ​<strong>https:// ​</strong>and ​<strong>http://​</strong>? What is the encryption standard used by them, if any?</li>

 <li>Download the file <u>​</u><a href="https://wiki.wireshark.org/SampleCaptures?action=AttachFile&amp;do=get&amp;target=mysql_complete.pcap"><strong>mysql_complete_pcap</strong></a><strong><u>​</u></strong><a href="https://wiki.wireshark.org/SampleCaptures?action=AttachFile&amp;do=get&amp;target=mysql_complete.pcap">.</a> Is it encrypted? Please justify.</li>

 <li>Download the file <u>​</u><a href="https://wiki.wireshark.org/SampleCaptures?action=AttachFile&amp;do=get&amp;target=mysql-ssl-larger.pcapng"><strong>mysql-ssl-larger.pcapng</strong></a><strong><u>​</u></strong><a href="https://wiki.wireshark.org/SampleCaptures?action=AttachFile&amp;do=get&amp;target=mysql-ssl-larger.pcapng">.</a> Is it encrypted? Please justify.</li>

 <li>Download the zipped file <a href="https://wiki.wireshark.org/SampleCaptures?action=AttachFile&amp;do=get&amp;target=snakeoil2_070531.tgz"><strong>tgz</strong></a><u>​ </u><strong>​</strong>. Extract the content in your local folder. Load the .pcap file in wireshark. Is it encrypted?</li>

 <li>Perform the decryption of the .pcap file as demonstrated in class by the instructor.

  <ol>

   <li>What frame number requests the image apache_pb.png?</li>

   <li>Does the server provide the image? What is the status code that implies the response has payload?</li>

   <li>Attach the image apache_pb.png to your report.</li>

  </ol></li>

 <li>What is the response that the server provided when requested for openlogo-25.jpg? Can you see the html code sent as a response? If yes, copy and paste it in a .html file and load it in your</li>

</ol>

favourite browser. Attach the screenshot of how the response looks like in the web browser.

<h1>Subtask 4 (Vulnerability Analysis)</h1>

The following assignment is to be done at the ​<strong>students own machine​</strong>. You do not have permission and user rights to do this on campus machines. Please make sure that you do not reveal any important information to your reports when you attach screenshots. (Please blur out any sensitive information)

<ol start="18">

 <li>The first thing that you will do is capture packets. You can use wireshark or tcpdump to capture packets. While you can capture packets from wireshark, I suggest you to use tcpdump so that you can be familiar with a new tool. Following are the procedures that you will follow:</li>

 <li>Find the interface that is connected to the internet. Do ​<strong>ifconfig ​</strong>in the terminal and select the one which is connected to the internet. Wireshark should show you the interface in its GUI.</li>

 <li>Start packet capture in tcpdump using ​<strong>tcpdump -i &lt;interface&gt; -s 65535 -w &lt;filename&gt;​</strong>. Or select the bluefin below File menu in wireshark after you select the interface if you wish to use wireshark.</li>

 <li>Please visit the website <u>​</u><a href="http://weevil.info/">http://weevil.info/</a><u>​</u> ​What is wrong with this website? 4. After it is completely loaded, stop the capture. You can select the button in Wireshark GUI or kill the tcpdump process if you are using tcpdump.</li>

 <li>Load the file in wireshark. If you are using wireshark, it is already loaded. 6. Try to find at least two images that are sent by the server to your machine and attach them to your report.</li>

 <li>What are the vulnerabilities of the website that you can see right away? 8. Repeat similar operation for <u>​</u><a href="https://www.foxnews.com/">https://www.foxnews.com/</a><a href="https://www.foxnews.com/">.</a><u>​</u> Attach two images sent from the server to your machine if you can.</li>

</ol>


