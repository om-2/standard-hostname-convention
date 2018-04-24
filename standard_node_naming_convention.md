# Standard Node Naming Convention

#### It should be :

* **Logical**
  - It is important to remember that host names should not reflect a specific device, but rather, 
    be a logical identifier of a device in the overarching infrastructure. 
    This allows for schemes to be teleported across environments.

* **Scalable**
  - The scheme must be able to scale, accommodating not just growth, but also shrinkage.

* **Human Readable**
  - The scheme must be readable and descriptive enough for a Human to consult a site-book 
    for further documentation about the object(s).

* **Machine Readable**
  - The scheme must remain easily parse-able and dynamically generate-able 
    by a machine for automation purposes.

* **Authoritative**
  - Identifiers such as locations, or VLAN tags must always match with 
    an authoritative source, such as a site-book.

#### Furthermore :
* The DNS hierarchy should always properly reflect the naming scheme. 
  In the event that a specific service on a host should need to be referenced, 
  a CNAME record shall be used.




## Network Devices and Interfaces

### Physical Chassis

* [type]-[layer]-[serial]

For example, a redundant distribution switch on a campus could be named the following.

* sw-ds-02.bldg4.campus02.example.com


#### Example References:

#### Physical Chassis Types
| Denotation  |   Explanation |
| --------- | ------------- |
|rt          |   Router |
|sw          |   Switch |
|fw          |   Firewall Appliance |
|ap          |   Access Point |

#### Layer Types
|Denotation  |   Explanation |
| ---------- | ------------- |
|ax         |   Access |
|ds          |   Distribution |
|co          |   Core |
|eg          |   Edge |


### Interfaces Descriptions
 
* [type]-[serial]--[destint]-[desthost] 

For example, a trunk interface for vlan 20 from an edge router (rt-eg-01.campus.example.com) 
to a core switch could look like the following.

* vl20--ge01.sw-co-01.campus.example.com

This is especially usefull for long P2P links, such as GRE, VPN or building interconnects. 


#### Example References:

##### Port Types
|Denotation  |  Explanation |
| ---------- | ------------ |
|ge          |  Gigabit Ethernet |
|fe          |  Fast Ethernet |
|gre         |  Generic Routing Encap. |
|vl          |  Virtual LAN |



## Servers and Endpoints

[type]-[layer]-[service/servicegroup]-[serial]  

For example, a server that was a host for development docker containers could be named the following:

* sv-dev-docker-01

The service may be explicit or denoted by a generic group if it is part of a larger groups of services, such as a failover cluster.  

As mentioned in section one, CNAMES should be used if needed to specify explicit services. 

#### Example References:

##### Type
|Denotation  |   Explanation |
| ---------- | ------------- |
|cl          |  A client endpoint device, such as a workstation.|
|sv          |  Server |
|ct          |  Container |
|iot          |  IOT Endpoint |

##### Logical Layer
|Denotation  |   Explanation |
| ---------- | ------------- |
|prod          |  Production |
|dev          |  Development |
|co           |  Core |
|dmz          |  DMZ Host |

##### Service(group)
|Denotation  |   Explanation |
| ---------- | ------------- |
| web          |  Generic Webserver |
| Apache          |  Apache Server |
| dns        |  Generic DNS |
| bind          | Bind DNS Server |



