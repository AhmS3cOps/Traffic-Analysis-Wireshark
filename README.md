# Traffic-Analysis-Wireshark 1.0

<h1>RedLine Stealer</h1>
RedLine Stealer is information-stealing malware that harvests login credentials and other sensitive data from a victim's Windows host. The malicious activity in this pcap is a RedLine Stealer infection from July 2023.

<h3>Quiz Questions</h3>
<ul>
  <li>
    What is the date and time in UTC the infection started?
  </li>
  <li>
    What is the IP address of the infected Windows client?
  </li>
  <li>
    What is the MAC address of the infected Windows client?
  </li>
  <li>
  What is the hostname of the infected Windows client?
    
  </li>
  <li>
  What is the user account name from the infected Windows host?
    
  </li>
  <li>
  What type of information did this RedLine Stealer try to steal?
    
  </li>
</ul>


<h2>Pcap Analysis</h2>
Answering Questions 1,2 and 3.
Firstly we apply basic web filtering, after doing this you notice that traffic is coming from a since source IP address which is "10.7.10.47" and from the time column we can see the time as well, we get the MAC address from the frame details pane.
answers are 
<ul>
<li>What is the date and time in UTC the infection started? : July 10, 2023, at 22:39 UTC.</li>
<li>  
What is the IP address of the infected Windows client? : 10.7.10.47
</li>
<li>
  What is the MAC address of the infected Windows client? : 80:86:5b:ab:1e:c4
</li>
</ul>
