# Functional Requirements

This section outlines the fundamental actions of the system.

## User Class 1 - User

### User Role - None

The functional requirements in this section apply to any user, regardless of authentication and authorisation, i.e. anybody can do them.

#### FR 1 - Access to software

| &darr; | &darr; |
| --- | --- |
| ID | **FR1** |
| TITLE | Download mobile application |
| DESC | Application should be free to download from Play Store (Android) or App Store (iOS) |
| RAT | Grant User hassle-free access to the app |
| DEP | None |

#### FR 2 - Access to listings

| &darr; | &darr; |
| --- | --- |
| ID | **FR2** |
| TITLE | Display listings immediately, regardless of login status |
| DESC | Anonymous AND known Users MUST see available listings in system immediately |
| RAT | New Users SHOULD see the immediate utility of system with minimum effort expended |
| DEP | FR1, FR3, FR4 |

Note: This should be implemented with an empty search (FR4) with no filters applied (FR3)

#### FR 3 - Filter listings

 
<table>
<tr><th>&darr;</th><th>&darr;</th><tr>
<tr> <td>*ID*</td><td>**FR3**</td></tr>
<tr> <td>*TITLE*</td><td>Filter listings</td></tr>
<tr>
<td>*DESC*</td>
<td>
User MUST be able to limit listings by:
  - type
    - sale
    - barter
    - donate
  - list date
  - category
  - price
  - proximity
  - BARGAINER reputation
  - hasTemplate
    - dropdown of templates in scope
  - tags
    - *listing dependent*: e.g. DVD episodes
</td>
</tr>
<tr>
<td>*RAT*</td>
<td>Allow User to narrow in on the product and service attributes they want quickly</td>
</tr>
<tr> <td>*DEP*</td><td>FR1, \{FR2 | FR4\}</td></tr>
</table>

Note: Filter operates on data that has been fetched from the database by FR2 or FR4. A filter applied BEFORE a User initiated search limits the result set, therefore another search (server access) must be performed to relax filter constraints, but not to tighten them.

#### FR 4 - Search listings

 
<table>
<tr><th class="a">&darr;</th><th>&darr;</th><tr>
<tr><td>*ID*</td><td>**FR4**</td></tr>
<tr><td>*TITLE*</td><td>Search listings</td></tr>
<tr>
<td>*DESC*</td>
<td>
Logged or unlogged User MUST be able to search listings for sepecific words and phrases in:
  - title
  - description
  - BARGAINER name
  - template (template is made up of unique identifiers for a product, e.g. an ISBN is a unique identifier for a book)
</td>
</tr>
<tr>
<td>*RAT*</td>
<td>Allow User to narrow in on the product and service attributes they want quickly</td>
</tr>
<tr><td>*DEP*</td><td>FR1, FR3</td></tr>
</table>

Note: Search uses FR3 as a base to limit search results and reduce network load. Filter listings (FR3) is subsequently constrained until it is reset and a new search performed.

#### FR 5 - View a listing

| &darr; | &darr; |
| --- | --- |
| ID | **FR5** |
| TITLE | View a listing |
| DESC | View a listing |
| RAT | Allow User to view a specific listing |
| DEP | FR1 |

Note: If listing belongs to current User:BARGAINER, display Edit/Update button.

#### FR 6 - OAuth 2.0 and OpenID Connect

| &darr; | &darr; |
| --- | --- |
| ID | **FR6** |
| TITLE | User authorisation and authentication (logging in) |
| DESC | Logging in MUST be accomplished using the delegation mechanism of OAuth and the authentication mechanism of OpenID Connect |
| RAT | Authentication, password storage, etc., are difficult problems. We externalise these difficulties to identity providers such as Google, Facebook, Twitter, and LinkedIn |
| DEP | FR1 |

### User Role - User:BARGAINER

Default User role upon login. The functional requirements in this section outline the default capabilities of a User engaged in the sale/purchase, exchange, donation/receival of baby goods and services.

#### FR 7 - Create a listing

 
<table>
<tr><th>&darr;</th><th>&darr;</th><tr>
<tr><td>*ID*</td><td>**FR7**</td></tr>
<tr><td>*TITLE*</td><td>Create a listing</td></tr>
<tr>
<td>*DESC*</td>
<td>
Listing may contain:
  - Title
  - Description
  - Long description
  - Images
  - External reference URLs
  - Category
  - Product or service template
    - tag list, e.g. if template possesses size and color tags, the User fills these with values
  - Listing Location (if different from User location)
  - Mode
    - Sale
      - Price
      - Mode of payment
      - Mode of physical exchange, i.e. delivery or meetup
        - Cost and timeframe of delivery
    - Barter
      - Open to offer OR enumerate one or more desired listing templates, e.g. iPhoneX AND a USB cable.
    - Donate
      - <T&C> <possible T&C templates for reuse i.e. no charity organisations, etc.>
      - Mode of physical exchange, i.e. delivery or meetup
        - Cost and timeframe of delivery
  - Start date
  - End date
</td>
</tr>
<tr>
<td>*RAT*</td>
<td>One of three core User functionalities of the platform, the others being the ability to view listings, and the ability to contact a lister</td>
</tr>
<tr><td>*DEP*</td><td>FR1, FR6</td></tr>
</table>

Note: The tag list of a product or service template should contain ALL the metrics necessary to define a specific product or service uniquely and unambiguously. E.g. A specific SD card might have the following enumerated tags: type:SDHC, storage:32GB, size:Micro, interface:UHS-II; and this range tag: rated_speed:300MB/s.

#### FR 7.1 - Add an image to listing

| &darr; | &darr; |
| --- | --- |
| ID | **FR7.1** |
| TITLE | Add an image to listing |
| DESC | Add product or service image to listing |
| RAT | Allow User to share visual representation of product or service |
| DEP | FR1, FR6, FR7 |

Note: Images with <large> storage requirements must be shrunk before sharing with server. The original image should be stored on the local mobile device. When a pair of Users connect on P2P chat over a listing, the associated original image may be shared P2P.

#### FR 7.2 - Apply a category to listing

| &darr; | &darr; |
| --- | --- |
| ID | **FR7.2** |
| TITLE | Associate listing with one category |
| DESC | Add a category to listing, one per listing |
| RAT | Categories allow quick and broad conceptualisation of what a listing is about |
| DEP | FR1, FR6, FR7 |

Note: Categories are heirarchical, i.e. Toiletries > vegan > shampoo

#### FR 8 - View all User owned listings

| &darr; | &darr; |
| --- | --- |
| ID | **FR8** |
| TITLE | View all User owned listings |
| DESC | View all listings the User owns as a list |
| RAT | Allow User to view all of his/her listings |
| DEP | FR1, FR6, FR3, FR4 |

Note: Implement by restricting listing owner to User on FR3 (filter) during an unconstrained FR4 (search)

#### FR 9 - Update a listing

| &darr; | &darr; |
| --- | --- |
| ID | **FR9** |
| TITLE | Update a listing |
| DESC | Update the details of a particular listing |
| RAT | Allow User to update fields on his/her listings |
| DEP | FR1, FR6 |


#### FR 10 - Add a phone number

| &darr; | &darr; |
| --- | --- |
| ID | **FR10** |
| TITLE | Add a phone number |
| DESC | Add a phone number to the account for internal use and identity verification purposes |
| RAT | If there are problems with the account, this contact can be used |
| DEP | FR1, FR6 |

#### FR 11 - Add an identity document

| &darr; | &darr; |
| --- | --- |
| ID | **FR11** |
| TITLE | Add an identity document |
| DESC | Add an identity document (ID, driver's licence, healthcare card, passport, utility bill, etc) to the account for identity verification purposes |
| RAT | Strong identity verification mechanism to allow Users to interact with the assurance of safety, or to know when that assurance is absent |
| DEP | FR1, FR6 |

#### FR 12 - Verify User:BARGAINER

| &darr; | &darr; |
| --- | --- |
| ID | **FR12** |
| TITLE | Verify the identity of a BARGAINER |
| DESC | Verify the identity of a BARGAINER through phone, email, (travel documents, identity cards: similar to Paypal requirements), etc. Each level of verification comes with a badge and increases status |
| RAT | For User security. Users should know when they are dealing with a legitimate and traceable person |
| DEP | FR1, FR6 |

#### FR 13 - Display User Profile

 
<table>
<tr><th>&darr;</th><th>&darr;</th><tr>
<tr><td>*ID*</td><td>**FR13**</td></tr>
<tr><td>*TITLE*</td><td>Display profile details</td></tr>
<tr>
<td>*DESC*</td>
<td>
Display User profile details:
  - Name
    - Delegation (from OAuth process)
  - Nickname
  - Profile picture
    - Delegation (from OAuth process)
  - Email(s)
    - Delegation (from OAuth process)
    - Primary (tag on an email)
    - Others
  - Phone number(s)
    - Primary
    - Others
  - Credit card and banking details link
</td>
</tr>
<tr>
<td>*RAT*</td>
<td>For User reference and assurance</td>
</tr>
<tr><td>*DEP*</td><td>FR1, FR6</td></tr>
</table>

#### FR 14 - Update User Profile

| &darr; | &darr; |
| --- | --- |
| ID | **FR14** |
| TITLE | Update profile details |
| DESC | Update User details listed in FR13 |
| RAT | User should be able to initiate a change in their own details |
| DEP | FR1, FR6 |

Note: Data is never deleted or overwritten, only flagged as deleted, i.e. it no longer appears, but still exists.

#### FR 14.1 - Update User Name

| &darr; | &darr; |
| --- | --- |
| ID | **FR14.1** |
| TITLE | Update User Name |
| DESC | Request a change of User Name |
| RAT | User should be able to initiate a change in their own details |
| DEP | FR1, FR6 |

Note: Name should match supplied identity documents, if any. All name changes must be recorded within a series of diffs. If no Nickname is set, the change will only be visible to others on Admin:CUSTOMERFOCUS approval. Limit to 10 name changes. Functionality disappears with reason displayed to user when limit exceeded. Admin:CUSTOMERFOCUS may unilaterally set a Name in the diff chain, once set it cannot be changed (advise User with message, similar to reaching limit).

#### FR 14.2 - Update User Nickname

| &darr; | &darr; |
| --- | --- |
| ID | **FR14.2** |
| TITLE | Update User Nickname |
| DESC | Change User Nickname. Immediate effect |
| RAT | User should be able to initiate a change of their own Nickname |
| DEP | FR1, FR6 |

Note: A search for previous Nickname should return new nickname with label "formerly old_nickname". Active and archived chats should also display "formerly old_nickname".

#### FR 15 - Display account information

| &darr; | &darr; |
| --- | --- |
| ID | **FR15** |
| TITLE | Display account information |
| DESC | Display the following information \{account name, link to profile, link to BBCoin topup, link to user_listings, link to BBCoin transactions, BBCoin balance, badges, reputation(BARGAINER, EDITOR, TRANSLATOR, CATALOGUER) \} |
| RAT | For user security. Users should know when they are dealing with a legitimate and traceable person |
| DEP | FR1, FR6 |

#### FR 16 - Top-up BBCoin balance

| &darr; | &darr; |
| --- | --- |
| ID | **FR16** |
| TITLE | Verify the identity of a BARGAINER |
| DESC | Verify the identity of a BARGAINER through phone, email, (travel documents, identity cards: similar to Paypal requirements), etc. Each level of verification comes with a badge and increases status |
| RAT | For user security. Users should know when they are dealing with a legitimate and traceable person |
| DEP | FR1, FR5 |



Placeholder

| &darr; | &darr; |
| --- | --- |
| ID | **FR1** |
| TITLE | . |
| DESC | . |
| RAT | . |
| DEP | . |
