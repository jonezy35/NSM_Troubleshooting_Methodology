# NSM_Troubleshooting_Methodology



 <u>3 Layers of troubleshooting</u>
1. Physical
    1. Power
    2. Dead ports/ cables
    3. Copper speed mismatch
    4. Fiber mode or wavelength mismatch
2. Networking
    1. Firewall Rules
    2. Switch Configs
3. Services
    1. Service status
    2. Configuration Files

<u>Methodology</u>
1. Verify The Problem
2. Determine which layer the problem exists at
    - Rule out layers the problem could not be at
    - Start with easiest issues that can be checked (power, cabling, service status)
3. Step through the kits data flow
    - Data is like water, the networks data has specific checkpoints it travels through before showing up in your SIEM.

<u>Diagnosing the problem</u>
1. Useful tools
    - IPMI - Intelligent Platform Management Interface - Out of band server management
        - Dell = iDRAC
        - HP = iLO
        - Supermicro = BMC
    - Splunk btool
        - ./splunk btool check
        - ./splunk btool inputs list
    - Elastic API
        - Kibana - GET /_cluster/health
        - Browser - https://master.dmssn.lan:9200/_cluster/health
        - Curl - curl -X GET "master.dmssn.lan:9200/_cluster/health"
        - More API's: https://www.elastic.co/guide/en/elasticsearch/reference/current/rest-apis.html

2. Researching the Problem
    - Support Pages
    - Book of zeek: https://docs.zeek.org/en/master/
    - Suricata docs: https://suricata.readthedocs.io/en/suricata-6.0.10/
    - Zeek docs: https://readthedocs.org/projects/zeek-docs/
    - Stack Overflow
    - Splunkbase

3. Configuration Files
    - Stop service if it's running
    - Save old configuration file (e.x. file.conf.old) before changing configs
    - Execute fix
    - Restart service
    - Verify fix


