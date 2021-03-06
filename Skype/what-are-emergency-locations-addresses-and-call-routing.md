---
title: What are emergency locations, addresses and call routing?
ms.prod: OFFICE365
ms.assetid: 589bf5f5-490a-4215-8588-99bab7d33e31
---


# What are emergency locations, addresses and call routing?

When you are configuring PSTN calling, it's required that an emergency address be assigned to each telephone number when you either get the phone number or when its assigned to a user to support emergency calling. Before assigning an emergency address to a phone number, an emergency address must be created and validated. Validation ensures that the emergency address is recognized that it is in a correct format that can be used by emergency response services. Optionally, a location within the emergency address can be added to provide a more specific location for the user. For example, the emergency location could be a floor, wing, or office that is linked to a specific emergency address. Even though emergency address are validated, locations aren't.
  
    
    


## What are emergency addresses?

An emergency address is required for active telephone numbers but this is dependent on the country/region. In the U.S. an emergency address is **required** when a number is assigned to a user. For other countries like in Europe, the Middle East and Africa (EMEA), an emergency address is **required** when you get the phone number from Office 365 or when it's transferred from another service provider or carrier.
  
    
    
An emergency address may often be referred to as a civic address, street address, or a physical address. It is the street or civic address of a place of business for your organization. For example,  *12345 North Main Street, Redmond, WA 98052*  . This address is used to route emergency calls to the appropriate dispatch authorities and to assist in locating the emergency caller. It's likely that you will need more than one emergency address if your business has more than one physical business location.
  
    
    
Validating an emergency address involves making sure that it is legitimate and correctly formatted for emergency response services. Although it's possible to create and save an emergency address that isn't validated, but only validated addresses can't be associated to a user. Once an emergency address is validated and saved, it can be assigned to a user. If you need to change a saved validated emergency address, you will need to create a new one.
  
    
    

## What are emergency locations?

Emergency locations are associated to an emergency address to give a more exact location within a building. An emergency location is typically a floor, building wing, or office number where the user is located. You can have an unlimited number of locations associated to an emergency address. 
  
    
    
When assigning a user an emergency address, it is actually a location ID that is referenced when you assign the address. The location ID includes the referenced emergency address (the street or civic address). A default emergency location is included with an emergency address for the case when in-building locations aren't needed. 
  
    
    

  
    
    

## What is emergency call routing?

Emergency addresses and locations are used during the process of routing emergency calls to the appropriate dispatch center when dispatching emergency first responders. When a Skype for Business user dials an emergency number, how the call is routed to the serving Public Safety Answering Point (PSAP) will vary by country/region. In some countries, like the U.S. and U.K. the calls will first be screened to determine the current location of the user before connecting the call to the appropriate dispatch center. In other countries/regions, calls will be routed directly to the dispatch center serving the phone number associated to the emergency caller.
  
    
    

## Creating, adding and assigning emergency locations and addresses to your users


1. **Plan for emergency locations** The first step is to plan for your emergency locations. You need to list all of your physical addresses. Then, based on that, it should be determined if locations for the emergency addresses are needed and if so, what they are. For example, if a business has 3 office buildings each with 4 floors, it is likely that there needs to be 3 emergency addresses, with floors 1-4 listed as a location for each.
    
  
2. **Create and validate your emergency locations** The next step is to create and validate your emergency addresses. When you create an emergency address, you can validate it. To create an emergency address, see [Add or remove an emergency address for your organization](add-or-remove-an-emergency-address-for-your-organization.md).
    
    > [!IMPORTANT]
      > Validating a street or civic address involves making sure that it is legitimate and correctly formatted. It is possible that a partially correct emergency address such as a mistyped name of the city, may pass still pass validation. The validation process uses all parts of a given address to determine if it contains enough information to route the call to the appropriate emergency dispatch center. If so, it will be returned as validated and then can be assigned to a phone number. 
3. **Get phone numbers** The next step is to get phone numbers for your users. You can do this by getting new phone numbers from Office 365 or by "porting" or transferring your existing phone numbers over to Office 365. To see the complete steps, see [Transfer phone numbers to Skype for Business Online](transfer-phone-numbers-to-skype-for-business-online.md).
    
  
4. **Assign phone numbers** The last step is to enable users to make and receive phone calls. To do this, you must assign a phone number to each user. See [Assign a phone number in Skype for Business](assign-a-phone-number-in-skype-for-business.md) to assign a phone number.
    
  

## See also


#### Other Resources


  
    
    
 [Skype for Business Online: Emergency Calling disclaimer label](https://go.microsoft.com/fwlink/?LinkID=692099)
  
    
    
 [Emergency calling terms and conditions](emergency-calling-terms-and-conditions.md)
  
    
    
 [Skype for Business Online PSTN services use terms](skype-for-business-online-pstn-services-use-terms.md)
