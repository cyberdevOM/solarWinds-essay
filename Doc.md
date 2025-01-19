## **Task 1: Solar winds Attack Case study**

The solar winds cyber attack was a landmark event int cybersecurity history and symbolized a turning point in the attack landscape proving that supply chain attacks were not only viable but widely successful. Spanning from September 2019 to March 26, 2020, this breach targeted SolarWinds, a significant provider of system management software, and resulted in widespread compromise of government and corporate systems worldwide.

##### **What happened?**
The attack was executed on SolarWinds' Orion software, a system management tool widely used by businesses and government agencies to monitor and manage IT infrastructures. The attack inserted a backdoor, codenamed "SunBurst", into Orion's software updates. When SolarWinds customers downloaded these updates, the malware would infiltrate their systems, granting attackers access to sensitive data and networks.

This breach leveraged a supply chain vulnerability, Where the attacker exploited a trusted software vendor to circulate malicious code to its clients. This method of distribution proved devastating due to the extensive usage of SolarWinds' products, enabling the attacker to compromise over 18,000 organizations, and gather an unprecedented amount of sensitive data.
##### **When Did It Occur?**
The known attack timeline began during September 2019, when the attackers successfully inserted their malicious code into the Orion platform. However it remained undetected for months, silently spreading to customers through routine software updates. The breach was eventually discovered on December 13th, 2020, when cybersecurity firm FireEye identified the unauthorised access to their own systems. 
FireEye traced the breach back to the compromised SolarWinds updates, uncovering a expansive and lengthy espionage operation.
##### **Who Was Behind It?**
An attack of this scale is often attributed to a joint effort of many groups, In the SolarWinds attack There were two named groups who have been suspected of their involvement however to this day nobody has claimed ownership of the attack.

The main party attributed responsibility is APT29, also known as Cozy Bear, a state-sponsored hacking group associated with the Russian Foreign Intelligence Service (SVR). Cozy Bear has a long history of cyber-espionage, including involvement in attempts to manipulate U.S. presidential campaigns. Their tactics are know for their stealth and focus on high-value targets, fitting this attack perfectly.

The Other group, Nobelium, has also been linked to the attack Nobelium is a shadowy, privately-funded hacking collective believed to have ties to Russia, China, or North Koreas cyber warfare groups. This group operates with advanced capabilities and has been associated with several high-profile cyber incidents. Microsoft's internal security analysts have since named nobelium in subsequent attacks, highlighting their sustained activity and expertise. 
While currently unknown where Nobelium operates out off however it is likely that they are a sub sector of one of the major Advanced Persistent threat groups likely with close ties to Cozy Bear (APT29), Fancy Bear (APT28), or Lazarus Group (APT38).

##### **How Did The Attack Happen?**
The SolarWinds attack was a sophisticated supply chain compromise targeting vulnerabilities in their software development pipeline. The attackers breached SolarWinds’ environment and embedded the SUNBURST backdoor into updates for its Orion IT management software. Cryptographically signed to appear legitimate, these updates exploited the trust customers placed in SolarWinds.

Once deployed, SUNBURST operated stealthily, mimicking normal Orion functions and blending into legitimate network activity. It delayed activation, communicated with command-and-control servers, and evaded detection by antivirus tools. SolarWinds’ insufficient security controls and lack of integrity checks in their build pipeline enabled this compromise, affecting thousands of government, corporate, and critical infrastructure customers.

The attackers prioritized privileged accounts to gain access to sensitive data while minimizing detection. By impersonating legitimate users and using advanced obfuscation techniques, they exfiltrated emails, files, and confidential information. This breach exposed major vulnerabilities in SolarWinds’ supply chain and highlighted the risks of third-party software, emphasizing the need for stricter security practices and zero-trust architectures
##### **Why Was It Done?**
The primary motive behind the SolarWinds attack was information gathering. By compromising Orion, the attackers gained system-level access to thousands of SolarWinds customer, including:
- U.S. government agencies such as the Department of Homeland Security, Department of Defence and the Treasury.
- Major corporations, including Microsoft, Cisco, and intel.
- Critical infrastructure providers and research institutions.
This level of access allowed attackers to harvest confidential data, monitor internal communications, and potentially disrupt critical operations. The attack's scale and targets suggest that it was not merely a financial crime but a coordinated espionage campaign, likely intended to bolster geopolitical and strategic advantages.

##### **The Fallout**
The discovery of the SolarWinds breach sent shockwaves across the cyber security community and beyond. Organisations scrambled to identify and mitigate the impact on their systems, while security experts analysed the sophisticated techniques used in the attack. The incident underscored the vulnerability of supply chains and the critical need for robust security measures in software development processes. 
For SolarWinds, the attack was a reputational disaster, prompting widespread scrutiny of its practices and the boarder software supply chain ecosystems. It also led to significant policy changes, including the Biden administration's executive order on improving the nation's cybersecurity in May 2021.

## **Task 2: Threat Analysis and Risk Assessment of the** **Solar Winds Attack**

![[Pasted image 20250116173941.png]]

In this first table we can see the risk of attack for critical assets and what they might be vulnerable to. This table takes a broad overview on vulnerabilities as to create a generalised look at the security of the asset.


![[Pasted image 20250116173908.png]]

#breif_descriptor_table2


## **Task 3: Cyber kill chain analysis**

#update_with_relivent_information

The SolarWinds attack can be mapped using the Lockheed martin Cyber Kill chain framework, which outlines the phases of a cyber attack. Below is the detailed mapping of the attack:

1. **Reconnaissance**
	The attackers, identified as APT29 (Cozy Bear) and Nobelium, conducted an in-depth reconnaissance to identify SolarWinds as a high-value target due to its widespread use by critical government agencies and corporations, notably large fortune 500 companies and technology firms. The attackers focused on SolarWinds' development pipeline, This phase involved gathering technical information about SolarWinds' Orion platform, its software update mechanisms, and potential weak points in its development environment.
	- **Tactics Used:** 
		- Open-Source Intelligence(OSINT): Publicly available documentation, employee social media profiles, and forums where scoured to uncover details about the company's operations and software development practices.
		- Phishing and Spear-Phishing: Employees, particularly those with  access to development environments, were targeted through personalized phishing campaigns
		- probing development systems: Network  scans and probing attempts were made to identify exposed or misconfigured endpoints with SolarWinds' infrastructure 

2. **Weaponization**
	In this phase, the attackers developed a malicious payload, later named SUNBURST, this Payload was designed to integrate seamlessly into SolarWinds' Orion platform. Once integrated SUNBURST would establish a backdoor and mimic legitimate traffic to evade detection.
	- **Technical Details:**
		- SUNBURST was crafted to embed malicious DLL files into Orion updates, ensuring the malware appeared as part of legitimate software.
		- The malware employed techniques like domain generation algorithms (DGA) to communicate with attacker-controlled command-and-control (C2) servers, complicating detection.
		- By leveraging stolen developer credentials or exploiting build server vulnerabilities, the attackers ensured their payload was signed and distributed alongside official updates.

3. **Delivery**
	The Compromised Orion software updates containing the SUNBURST malware were delivered to SolarWinds' Trusted update process. This delivery method turned SolarWinds into an unwitting distributor of malicious software.
	- **Tactics Used:** 
		- Supply chain Exploitation: By compromising SolarWinds' build process, attackers ensured that the malware would be widely distributed to approximately 18,000 organizations worldwide.
		- exploiting trust: The attackers relied on the inherent trust customers place in signed and verified software updates.

#clarify_attks_on_SW_and_attks_on_client
4. **Exploitation**
	Once customers installed the compromised Orion updates, the SUNBURST malware exploited the trust relationship to execute code and establish a foothold in their systems.
	- **Technical Aspects:**
		- The malware executed under the same permissions as the Orion application, often with elevated privileges.
		- SUNBURST exploited software trust to load its malicious DLL into memory and avoid detection by using legitimate processes.
		- Privilege escalation techniques were employed to access sensitive resources within compromised environments. 

5. **Installation**
	The SUNBURST malware established persistence by communicating with attacker-controlled C2 servers and installing itself in a manner that allowed it to evade security controls.
	- **Technical Details:**
		- Persistence Mechanisms: The malware leveraged legitimate services and processes to avoid detection, such as embedded itself in routine tasks performed by Orion.
		- C2 Communication Setup: The attackers utilized domain fronting and DNS tunnelling to establish encrypted communication with their servers, making traffic appear normal.

6. **Command and Control (C2)**
	The malware communicated with C2 servers to receive instructions, execute tasks, and facilitate further stages of the attack.
	- **Technical Aspects:**
		- Encrypted Communications: Traffic between SUNBURST and its C2 servers was encrypted and obfuscated to resemble legitimate network activity.
		- Modular Payloads: The attackers sent modular payloads to specific targets based on the value of their systems, enabling targeted exploitation.
		- Lateral Movement: Once established in the network, the malware enabled attackers to pivot to other systems by compromising additional credentials and exploiting trust relationships

7. **Actions On Objectives**
	The attackers used the foothold provided by SUNBURST to carry out their primary objectives, which included data exfiltration, espionage, and further compromise of high value assets and systems.
	- **Technical Aspects:**
		- Credential Harvesting: Attackers extracted credentials from memory and used tools like mimkatz to escalate privileges.
		- Lateral Movement: They exploited trust relationships between systems to move laterally within networks, targeting domain controllers and sensitive databases.
		- Data Exfiltration: Highly sensitive data, including emails and confidential documents, was extracted using encrypted channels to avoid detection.
		- Selective Targeting: Of the 18,000 affected organizations, attackers focused on approximately 100 high-value targets, demonstrating precise targeting capabilities.

**Conclusion**
The SolarWinds attack demonstrates the advanced tactics, techniques, and procedures (TTPs) used by nation-state actors like APT29 and Nobelium. By leveraging a supply chain vulnerability, the attackers successfully exploited the entire cyber kill chain, from reconnaissance to achieving their objectives. This breach underscores the importance of securing supply chains, implementing robust monitoring and fostering an adaptive security posture to mitigate such sophisticated threats.
This detailed analysis provides insight into the attackers’ methodologies, offering a blueprint for understanding and preventing similar breaches in the future.


## **Task 4: Threat modelling**

![[attack tree.jpeg]]

**Root Node**
- Objective: Compromise the SolarWinds server.

**Branch 1: Exploit Software development Environment**
1. **Gaining Unauthorized access  to developer credentials:**
	- Phishing campaigns targeting employees.
		- Links to: Exploit network infrastructure (if phishing gains VPN access).
	- Credential stuffing using breached database
		- Links to: Access source code repositories.
	- Keylogging malware planted on developer endpoints.
		- Links to: intercepting credentials for CI/CD pipeline

2. **Exploit vulnerabilities in development tools:**
	- Unpatched Jenkins or CI/CD systems.
	    - Links to: Malicious code injection into builds.
	- Exploiting weak source control (e.g., Git, SVN).
	    - Links to: Access repositories for code tampering.

3. **Social engineering to gain physical access:**
	- Impersonate IT staff to access development infrastructure.
	- Plant USB malware on machines in office spaces.
	    - Links to: Introducing backdoors or stealing credentials.

**Branch 2: Compromise Supply Chain**
1. 1. **Inject malicious code into software updates:**
    - Modify source code repositories.
        - Links to: Development environment vulnerabilities.
    - Manipulate build processes in CI/CD pipelines.
        - Links to: Exploiting developer credentials or insider threats.

2. **Introduce hardware or firmware backdoors in SolarWinds servers:**
    - Intercept hardware during transit.
        - Links to: Physical supply chain manipulation.
    - Tamper with firmware updates for SolarWinds devices.

3. **Hijack DNS or update servers:**
    - Redirect customers to malicious update servers.
    - Spoof legitimate update files with malicious ones.
        - Links to: Network perimeter compromise.

**Branch 3: Exploit Network Perimeter**
1. **Exploit unpatched vulnerabilities:**
    - Zero-day vulnerabilities in SolarWinds software.
        - Links to: Both insider threats and exploitation during transit.
    - Target unpatched VPNs or firewalls.
        - Links to: Phishing to gain initial foothold.

2. **Distributed Denial of Service (DDoS) to mask activities:**
    - Simultaneously distract defenders.
        - Links to: Planting backdoors during the attack.

3. **Weak password policies or credential reuse:**
    - Attack publicly exposed management systems or APIs.
        - Links to: Insider threats if credentials are compromised.

**Branch 4: Exploit Insider Threats**
1. **Bribe or coerce employees:**
    - Gain insider access to source code repositories or build systems.
    - Request employees to share credentials or introduce malware.
        - Links to: Supply chain compromises.

1. **Recruit or plant malicious insiders:**
    - Developers deliberately insert backdoors.
    - Operations staff modify DNS or update servers.

1. **Social engineering insider collusion:**
    - Trick employees into running malware or exposing data.
        - Links to: Development environment exploitation.

**Branch 5: Exploit Misconfigurations**
1. **Unsecured build pipelines:**
    - Misconfigured permissions on source code repositories.
    - Weak network segmentation between critical systems.

1. **Insufficient logging or monitoring:**    
    - Allow attackers to remain undetected for longer.
        - Links to: Network perimeter exploitation.

1. **Lack of integrity checks:**
    - Enable unnoticed tampering with updates or builds.

**Key Links Between Branches**
- **Developer Credentials → Source Code Repositories → Malicious Code Injection:** Compromised developer credentials provide access to source code repositories, where attackers can inject malicious code.
- **Network Perimeter Exploitation → Update Distribution Manipulation:** Vulnerabilities in exposed systems can give attackers the ability to manipulate update distribution servers.
- **Insider Threats → Supply Chain Tampering:** Malicious insiders with build pipeline access can enable the injection of malware.
- **Misconfigurations → Delayed Detection:** Poor logging and monitoring allow attackers to maintain persistence without triggering alerts.

I have included a visual and and text based attack tree diagram to the best of my ability.

The attack tree shows the 4 possible attack vectors, and their tree nodes, noting links between main branches and nodes as well as between individual nodes. this is best shown in a the visualised attack tree diagram that I have included as well as linked [here](https://github.com/cyberdevOM/uni_work_backup/blob/f9853fa9337093439bf6974d47ef433c15893390/year%202/mod%202/coursework/attack%20tree.jpeg). 

I was unable to use the proper attack tree notation due to the limitations of the program I use however I still believe that it provides a valuable visual representation.
## **Task 5: Pre-breach Infrastructure diagram**
#change_to_inc_internet #show_customer_networks
![[Pasted image 20250118175950.png]]
**Network diagram analysis**
- **Routing and switching**
	- Devices: 2911 Router, 2950T-24 Switches
	- Purpose:
		- The 2911 Router facilities external communication and is responsible for routing traffic between subnets and external networks.
		- The 2950T-24 Backbone Network Switch Acts as a core switch interconnecting all other subnets, This High speed network switch handles inter-subnet traffic, providing routing and switching between marketing, management, development, and security subnets.
		- Each Subnet has its own 2950T-24 network switch to handle devices and local subnet traffic.
- **Marketing:**
	- Devices: 
		- Marketing PCs (PC1, PC2)
		- Media server (Meraki-Server)
		- Printer (Marketing Printer)
	- Switch: 2950T-24 Marketing
	- Purpose: Enables devices to connect to the subnet and access the media server and marketing printer. 
- **Management**
	- Devices:
		- Management PCs (PC1, PC2, PC3)
	- Switches 2950T-24 Management
	- Purpose: allows for centralised control and management tasks, Also allows for isolated control over connection to external and internal resources for security.
- **Development**
	- Devices:
		- Development PCs (Dev PC1, Dev PC2)
		- Servers (Distribution Server, Web Server, Dev Server)
	- Switch 2950T-24 Development
	- Purpose:
		- Provides connectivity for software development and testing.
		- Includes servers for hosting development applications and distribution purposes. (In a real world scenario these would likely be off site or hosted by a third party.)
- Security
	- Devices:
		- SOC PCs (PC1, PC2)
	- Switch: 2950T-24 Secure
	- Purpose: 
		- Dedicated to the SOC team for monitoring analysis and incident response.
		- stricter access controls and network monitoring tools.
- **VLANs**
	The configuration of the following VLANs is designed to enable traffic isolation and increase security. 
	Each VLAN has access to relevant areas of the network for example, Development VLAN 30 has access to the marketing media server to enable developers to use graphical resources created by the marketing and design teams. They however do not have access to the SOC or management Devices
	- VLAN 10: Marketing
	- VLAN 20: Management
	- VLAN 30: Development
	- VLAN 40: Security/SOC

This Network Diagram has been stripped back to a simplistic interpretation of how a full network would look for SolarWinds. The development server and Distribution server would likely be hosted on prem due to the little overhead Distributing software would be, and Development server would likely contain sensitive pre-release builds of software that if released into public domain would pose a security incident for SolarWinds. Because of this Hosting on prem would allow them to maintain control over the hardware and software while managing the security of its data.

Key attack vectors for the SolarWinds hack 2020 would be the development server and the distribution server, these are both included in the network model. The development server would have access to privileged development builds of the Orion software and its development environment, attackers that gain access to this would be able to manipulate the Orion software development builds in any way they see fit. This was the approach taken in the 2020 hack of SolarWinds That allowed the attackers to implement the SUNBURST malware. From here software builds are likely tested very little and then pushed to its production version of the Orion application.
## **Task 6: Post-breach infrastructure diagram**

![[Pasted image 20250118172744.png]]
**Network Diagram Analysis**
- **Routing and switching**
	- Devices: 2911 Router, 2950T-24 Switches
	- Purpose:
		- The 2911 Router facilities external communication and is responsible for routing traffic between subnets and external networks.
		- The 2950T-24 Backbone Network Switch Acts as a core switch interconnecting all other subnets, This High speed network switch handles inter-subnet traffic, providing routing and switching between marketing, management, development, and security subnets.
		- Each Subnet has its own 2950T-24 network switch to handle devices and local subnet traffic.
- **Marketing:**
	- Devices: 
		- Marketing PCs (PC1, PC2)
		- Media server (Meraki-Server)
		- Printer (Marketing Printer)
	- Switch: 2950T-24 Marketing
	- Purpose: Enables devices to connect to the subnet and access the media server and marketing printer. 
- **Management**
	- Devices:
		- Management PCs (PC1, PC2, PC3)
	- Switches 2950T-24 Management
	- Purpose: allows for centralised control and management tasks, Also allows for isolated control over connection to external and internal resources for security.
- **Development**
	- Devices:
		- Development PCs (Dev PC1, Dev PC2)
		- Servers (Distribution Server, Web Server, Dev Server)
	- Switch 2950T-24 Development
	- Purpose:
		- Provides connectivity for software development and testing.
		- Includes servers for hosting development applications and distribution purposes. (In a real world scenario these would likely be off site or hosted by a third party.)
- Security
	- Devices:
		- SOC PCs (PC1, PC2)
	- Switch: 2950T-24 Secure
	- Purpose: 
		- Dedicated to the SOC team for monitoring analysis and incident response.
		- stricter access controls and network monitoring tools.
- Testing
	- Devices: 
		- Testing Servers (Server1,2)
		- Testing backup server, 
	- Switch: 2950T-24 Testing
	- Purpose:
		- Dedicated air gapped network for testing new hardware, software or third party tools.
		- Redundant Development environment servers and Dedicated server cluster for git and version control, this can work along side a automated code change review for security.
- Production
	- Devices:
		- Distribution servers
		- Web servers
		- DNS 
	- Switch: 2950T-24 Prod (DMZ)
		- Network Locked down to a DMZ to further prevent access to internal network from external users
	- Purpose:
		- Dedicated servers for distribution and web hosting.
		- Air gapped to prevent outside interference and tampering.
		- scalable web servers to compensate for low and high traffic and help mitigate DDoS attack vulnerability (acting as a buffer).
- **VLANs**
	The configuration of the following VLANs is designed to enable traffic isolation and increase security. 
	Each VLAN has access to relevant areas of the network for example, Development VLAN 30 has access to the marketing media server to enable developers to use graphical resources created by the marketing and design teams. They however do not have access to the SOC or management Devices
	- VLAN 10: Marketing
	- VLAN 20: Management
	- VLAN 30: Development
	- VLAN 40: Security/SOC
	- VLAN 50: Testing
	- VLAN 60: Production (DMZ)

- External Networking
	- External Switching (WAN)
	- DNS servers (1,2,3)
	- External LAN networks

In this network diagram I have modified the existing structure to further help mitigate the risk of attack on crucial assets as well as isolating them to prevent threat actors moving from an internal device onto the server that would then allow them to bypass security measures.

To further improve the security I would use strict access control and logging to help detect intrusion, possibly using AI to track behavioural aspects of high level accounts and alert to unusual behaviour. 
I would also introduce multi factor authentication for all developers and accounts with high level permissions or wide ranging access. using both physical and online access tokens.
## **Task 7: Security Assurance Architecture**


## **Task 8: Stix SDO model**