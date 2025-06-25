---
title: Digital Emblem (DIEM) Use Cases 
abbrev: DIEM Use Cases
docname: draft-fdhwm-digital-emblem-use-cases-00
category: info

ipr: trust200902

stand_alone: yes
pi: [toc, sortrefs, symrefs]

author:
 -
    ins: R. Fainchstein
    name: Rahel Fainchstein
    org: JHU/APL
    email: rahel.fainchstein@jhuapl.edu
 -
    ins: C. Deccio
    name: Casey Deccio
    org: Brigham Young University
    email: casey@deccio.net
 -
    ins: B. Haberman
    name: Brian Haberman
    org: Fastly
    email: brian@innovationslab.net
 -
    ins: B. Woodcock
    name: Bill Woodcock
    org: PCH
    email: woody@pch.net
 -
    ins: A. Mankin
    name: Allison Mankin
    org: PCH
    email: allison.mankin@gmail.com
 

normative:
  RFC2119:
  RFC8174:

informative:
  BLUEHELMET:
    target: https://guide-humanitarian-law.org/content/article/3/peacekeeping/
    title: The Practical Guide to Humanitarian Law
    author:
       org: Doctors Without Borders
  BLUESHIELD:
    target: https://www.unesco.org/en/heritage-armed-conflicts/enhanced-protection-cultural-property-highest-importance-humanity
    title: Enhanced Protection - Cultural Property of Highest Importance to Humanity
    author:
       org: United Nations Educational, Scientific and Cultural Organization
  REDCROSS:
    target: https://www.icrc.org/en/doc/assets/files/other/protection_emblems.pdf
    title: The Protection of the Red Cross / Red Crescent Emblems
    author:
       org: International Committee of the Red Cross
  PRESS:
    target: https://safety.rsf.org/appendix-i-protection-of-journalists-in-war-zones/
    title: RSF Resource for Journalists' Safety
    author:
       org: Reporters Without Borders
  DIPLOMAT:
    target: https://www.law.cornell.edu/cfr/text/19/148.83
    title: Personnel of Foreign Governments and International Organizations and Special Treatment for Returning Individuals
    author:
       org: Cornell Law School - Legal Information Institute
    
--- abstract

International law defines a number of emblems, such as the blue helmets of United Nations peacekeeping forces,
the blue and white shield of UNESCO, and the Red Cross of the International Committee of the Red Cross, as indicative
of special protections under the Geneva Conventions. Similar protections attach to journalists who wear "Press" protective
emblems on the battlefield, under Article 79 of Protocol I of the Geneva Conventions and Resolution 2222 of the United
Nations Security Council. The emblems of national governments and inter-governmental organizations protect diplomatic
pouches, couriers, and envoys under the Vienna Convention on Diplomatic Relations. Other marks enjoy protections against
mis-use under the Paris Convention, the Madrid Protocol, and the Trade-Related Aspects of Intellectual Property Rights.

This document provides an initial summary of problems placing emblems into digital use cases 
and documents identified requirements
from a number of stakeholders with active or potential interests in digital emblems.
To Do: align abstract as well as document with the WG charter.

--- middle

# Introduction

International law defines a number of emblems, such as the blue helmets of United Nations (UN) peacekeeping forces {{BLUEHELMET}},
the blue and white shield of UNESCO {{BLUESHIELD}}, and the Red Cross of the International Committee of the Red Cross (ICRC) {{REDCROSS}},
as indicative of special protections under international law. Similar protections attach to journalists who wear "Press" protective
emblems on the battlefield {{PRESS}}. The emblems of national governments and inter-governmental organizations protect diplomatic
pouches, couriers, and envoys {{DIPLOMAT}}, and international law protects certain marks against counterfeiting.

## Conventions

The key words "MUST", "MUST NOT", "REQUIRED", "SHALL", "SHALL NOT", "SHOULD", "SHOULD NOT", "RECOMMENDED",
"NOT RECOMMENDED", "MAY", and "OPTIONAL" in this document are to be interpreted as described in
BCP 14 {{RFC2119}}{{RFC8174}} when, and only when, they appear in all capitals, as shown here.

# Threat Model for Physical Emblems

Physical emblems have served a number of key functions over hundreds of years. The design/use of those physical emblems were limited
by the available resources and capabilities during the time of their inceptions. As technology advances and newer capabilities become
available, it is beneficial to examine limitations with existing emblems and identify potential needs going forward.

The following describes a number of weaknesses with physical emblems.

## Authenticity

It is generally not possible to evaluate the authenticity of a physical emblem in real-time. Physical emblems do not carry any type of
attestation from an authorized party indicating the validity of emblem. Mis-use of a physical emblem requires a post-facto investigation.

## Visibility

Physical emblems may not always be visible to an observing party. They can be difficult or impossible to see in the dark. The physical emblem
may be deployed on the opposite side of an object from an observing party. They may be difficult to observe from a distance or at
an oblique angle. The visibility of a physical emblem may be affected by wear, vandalism, or obfuscation.

## Mis-use

Physical emblems do not provide sufficient context to indicate the validity of their observed use. Physical emblems requested for use in a specific
location and/or at a certain time can be re-used at other locations or times that are not authorized. No mechanism exists to correlate the
validity of a physical emblem with specific locations, times, items, or people subject to protection. Such abuse is similar to known security
attacks (replay, time-shifting, and location-shifting attacks).

## Management

As noted above, potential mis-use of a physical emblem typically requires a post-facto investigation. There is no mechanism to revoke
the instance of a physical emblem that has been abused, compromised, or is no longer valid.

# Notional Requirements for Digital Emblems

The above list of weaknesses highlights the need for an emblem approach that meets a number of requirements to perform its function
properly under international law. Because there are multiple use cases for digital emblems, some of which are fundamentally different
from one another, it is not presumed that any one use of a digital emblem would necessarily have every single one of these requirements
for a given implementation.

## Identification Requirements

A digital emblem capable of acting as an official marking of legal significance needs to be identifiable by its intended legal purpose
and what assets it applies to. To do this, digital emblems...

- MUST provide a clearly detectable and unambiguous marking mappable to enable verification,
- MUST be machine-readable to enable automated verification,
- MUST be capable of carrying a visual representation of the physical emblem it represents,
- MUST carry an unambiguous indication of the international law or laws conferring protection upon the entity marked with the emblem,
- MUST be possible to associate with a range or specific quantity of persons or items,
- MUST be possible to associate with online services (e.g., websites, email servers, databases),
- MUST be possible to associate with data in transit or at rest,
- MUST be possible to associate with network-addressable equipment (e.g., routers, servers, laptops, IoT devices),
- MUST be possible to associate with a physical object (e.g., building, vehicle, container),
- MUST be possible to associate with a person or group of people

## Distribution Requirements

A digital emblem applicable to a variety of physical and digital assets will need to support a variety of discovery mechanisms
to ensure emblem verification is a practical process international law can enforce. Practicality can mean multiple things, including
minimizing the risk that verifying emblems will disclose verifier presence or behavior, minimizing the cost of verifying digital
emblems, and ensuring universal access to emblem-bearing for legally entitled assets.

To accomplish practical emblem distribution, digital emblems...

- MUST NOT impose an undue cost to verify,
- MUST NOT impose an undue cost to apply to or remove from an asset,
- MUST NOT impose an undue cost to acquire authority to deploy,
- MUST NOT require verifiers of the emblem to reveal to the emblem bearer that existence checking is occurring,
- SHOULD be possible to view an emblem in-band via a communications network, optically (e.g., QR code), or wirelessly (e.g., RFID).

## Trust model requirements

A digital emblem needs to be trustworthy in order to provide any value. This means that parties verifying the presence of emblems need to
know that the asset bearing an emblem is entitled to do so for the declared asset, time frame, and other scopes. Therefore, digital emblems...

- MUST be authorized by a party that has the legal authority to issue it,
- MUST identify the authorizing party that issued it to ensure accountability of emblem use,
- MUST carry an unambiguous indication of the international law or laws conferring protection upon the entity marked with the emblem,
- MUST be capable of providing a reference to additional relevant information (e.g., photographs, unique identifiers) which can be used to corroborate the association of the digital emblem with the entity bearing it,
- MUST be revocable when they are no longer valid,
- MUST be restrictable by temporal scope,
- MUST be restrictable by geographic scope,
- MUST be robust against being replayed by invalid bearers,
- MUST be robust against forgery of its various properties.

# IANA Considerations

This document makes no requests of the IANA.

# Security Considerations

A key part of this document highlights the risks surrounding physical emblems. Technical implementations of digital emblems will undoubtedly
incur their own security considerations. However, this document does not propose technical solutions; it enumerates the use cases that justify
creating technical solutions and what requirements are imposed on such solutions.

# Contributors
Tony DeSimone, Kerstin Vignard, and Erin Hahn provided insight into the legal and policy issues surrounding emblems.
Tommy Jensen, Felix Linker and Mauro Vignati provided many of the requirements that derive from digital asset use cases.

# Acknowledgments

--- back


# Use Cases for a digital emblem
Digital emblems are verifiable labels that can be associated with an entity so
that a verifier can prove that the entity (person, place, or thing) has some property the digital emblem represents.
This is a list of use cases that necessitate the creation of one or more standards for
digital emblems to be used to express some status of the entity bearing them.
Each use case contains a list of potential attributes to associate with the entity as a
part of the emblem. It is assumed that each use case would contain a link or reference to the
law, regulation, or policy that governs the protections granted under the emblem.

These use cases come from discussions with the organizations identified. This is a representative (not exhaustive) list
of use cases for a digital emblem.

## International Committee of the Red Cross (ICRC)
The ICRC is responsible for the visual Red Cross, Red Crescent, and Red Crystal emblems
used to label physical assets such as buildings and vehicles so that wartime combatants know
that International Humanitarian Law (IHL) forbids attacking that asset. The ICRC has been challenging 
private industry and academic researchers to create a digital equivalent to these visual 
emblems that can be used to label digital assets as protected under IHL the same way they
can label physical assets today.

* Indication of location
* Textual description

The ICRC has shared the following concrete use cases as part of their industry
and academic research engagement.

### Labeling web servers
Ensuring that attackers targeting a server hosting websites the attacker wishes to compromise know that the server hosting those sites is IHL protected.

### Labeling personal-use devices
Doctors use laptops to process IHL protected data both on hospital premises and on the move.

### Labeling power-constrained devices
IoT devices are used to manage various equipment within hospitals, and their power constraints may pose unique limitations on digital emblem solutions.

### Labeling networks from within
A device on a network that was compromised by a non-network path (such as malware loaded from a USB device) needs to discover that it compromised a network that is IHL protected (distinct from discovering the compromised device is protected).

### Labeling networks from without
Attackers trying to compromise a network through a network path can discover an emblem for an IP address for a NAT or gateway behind which are IHL protected assets.

### Miscellaneous
Other valuable use cases may exist across the following areas: 
protections of buildings (e.g., hospitals), people (e.g., aid workers), vehicles
(e.g., ambulances), objects (e.g., medical devices), digital services (e.g., family
reunification services), and data at-rest & in-transit. Permission to use an emblem is delegated
to each UN member nation.

## United Nations
UN Peacekeepers may require protective markings in theater as well as facilities associated
with the mission.

## United Nations Educational, Scientific, and Cultural Organization (UNESCO)
Requires protections for items of cultural heritage, both physical and digital. Priority is on
buildings and physical artworks. These can be denoted with location information, descriptions,
and linked images. There is a special concern with repatriating stolen works, which would benefit
from a provenance trail via an emblem. Their is also an interest in ensuring that a physical instantiation
of an emblem accompany each artwork and leverage the digital emblem to track the current location and
any special handling needed.

* Indication of location
* Image(s)
* Textual description
* Chain-of-custody / provenance

## Organization for the Prohibition of Chemical Weapons (OPCW)
Requires protection of Schedule 1 chemicals in transit between signatory countries for research,
medical, pharmaceutical, or protective purposes. Emblem would identify place, date, and volume
of production. Also a need to encrypt the description/characteristics of the items for access only
by the receiving customs agencies and material handlers. This encryption precludes other actors from
determining the contents being transported.

* Indication of location (dynamic as materials are moved)
* Indication of quantity
* Textual description

## International Atomic Energy Agency (IAEA)
IAEA administers several treaties, especially related to the controlled shipment of atomic fuels and wastes
across borders. Similar use case as OPCW.

## Basel Convention
Regulates the trans-boundary movement of hazardous wastes. Use cases are functionally identical to OPCW and IAEA.

## Press
Journalists in conflict zones require protective markings that indicate their status as a non-combatant.

## World Intellectual Property Organization (WIPO)
WIPO administers 26+ treaties with different protections for different things. Brands that are
protected under international law (e.g., Madrid Protocol) can mark their shipments with an emblem
allowing customs agents to positively identify legitimate products.

* Copyright/Brand image
* Textual description
* Chain-of-custody / provenance

## International Civil Aviation Organization (ICAO)
Requires protection of civil aviation flights and the ability to assert that they are not dual-use (i.e., not
carrying military cargo). Digital emblem would carry a geographic description of the flight plan, its current
location, and an indicator of its identity (i.e., tail number). Potential need for the emblem to reference a flight manifest.

* Indication of location
  * Flight plan is static
  * Current location is dynamic
* Textual description (i.e., manifest, identifying characteristics such as tail number)

## World Health Organization (WHO)
Similar use case as the ICRC.
