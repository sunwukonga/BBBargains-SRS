# Functional Requirements

This section outlines the fundamental actions of the system.

## User Class 1 - User

### FR 1 - Access to software

| &darr; | &darr; |
| --- | --- |
| ID | **FR1** |
| TITLE | Download mobile application |
| DESCRIPTION | Application should be free to download from Play Store (Android) or App Store (iOS) |
| RATIONALE | Grant User hassle-free access to the app |
| DEPENDENCY | None |

### FR 2 - Access to listings

| &darr; | &darr; |
| --- | --- |
| ID | **FR2** |
| TITLE | Display listings immediately, regardless of login status |
| DESCRIPTION | Anonymous AND known Users MUST see available listings in system immediately |
| RATIONALE | New Users SHOULD see the immediate utility of system with minimum effort expended |
| DEPENDENCY | FR1 |

### FR 3 - Filter listings

 
<table>
<tr><th>&darr;</th><th>&darr;</th><tr>
<tr> <td>*ID*</td><td>**FR3**</td></tr>
<tr> <td>*TITLE*</td><td>Filter listings</td></tr>
<tr>
<td>*DESCRIPTION*</td>
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
<td>*RATIONALE*</td>
<td>Allow User to narrow in on the product and service attributes they want quickly</td>
</tr>
<tr> <td>*DEPENDENCY*</td><td>FR1, \{FR2 | FR4\}</td></tr>
</table>

Note: Filter operates on data that has been fetched from the database by FR2 or FR4. A filter applied BEFORE a User initiated search limits the result set, therefore another search (server access) must be performed to relax filter constraints, but not to tighten them.

### FR 4 - Search listings

 
<table>
<tr><th>&darr;</th><th>&darr;</th><tr>
<tr><td>*ID*</td><td>**FR4**</td></tr>
<tr><td>*TITLE*</td><td>Search listings</td></tr>
<tr>
<td>*DESCRIPTION*</td>
<td>
Logged or unlogged User MUST be able to search listings for sepecific words and phrases in:
  - title
  - description
  - BARGAINER name
  - template (template is made up of unique identifiers for a product, e.g. an ISBN is a unique identifier for a book)
</td>
</tr>
<tr>
<td>*RATIONALE*</td>
<td>Allow User to narrow in on the product and service attributes they want quickly</td>
</tr>
<tr><td>*DEPENDENCY*</td><td>FR1, FR3</td></tr>
</table>

Note: Search uses FR3 as a base to limit search results and reduce network load. Filter listings (FR3) is subsequently constrained until it is reset and a new search performed.

### FR 5 - OAuth 2.0 and OpenID Connect

| &darr; | &darr; |
| --- | --- |
| ID | **FR5** |
| TITLE | User authorisation and authentication (logging in) |
| DESCRIPTION | Logging in MUST be accomplished using the delegation mechanism of OAuth and the authentication mechanism of OpenID Connect |
| RATIONALE | Authentication, password storage, etc., are difficult problems. We externalise these difficulties to identity providers such as Google, Facebook, Twitter, and LinkedIn |
| DEPENDENCY | FR1 |

### FR 6 - Create a listing

 
<table>
<tr><th>&darr;</th><th>&darr;</th><tr>
<tr><td>*ID*</td><td>**FR6**</td></tr>
<tr><td>*TITLE*</td><td>Create a listing</td></tr>
<tr>
<td>*DESCRIPTION*</td>
<td>
Listing may contain:
  - Title
  - Description
  - Long description
  - Images
  - External reference URL
  - Category
  - Product or service template
    - tag list, e.g. if template possesses size and color tags, the User fills these with values
  - Listing Location (if different from User location)
  - Mode
    - Sale
      - Price
      - Mode of payment
      - Mode of physical exchange, i.e. delivery or meetup
    - Barter
      - Open to offer OR enumerate one or more desired listing templates, e.g. iPhoneX AND a USB cable.
    - Donate
      - <T&C>
      - Mode of physical exchange, i.e. delivery or meetup
  - Start date
  - End date
  
</td>
</tr>
<tr>
<td>*RATIONALE*</td>
<td>One of three core User functionalities of the platform, the others being the ability to view listings, and the ability to contact a lister</td>
</tr>
<tr><td>*DEPENDENCY*</td><td>FR1, FR5</td></tr>
</table>

Note: The tag list of a product or service template should contain ALL the metrics necessary to define a specific product or service uniquely and unambiguously. E.g. A specific SD card might have the following enumerated tags: type:SDHC, storage:32GB, size:Micro, interface:UHS-II; and this range tag: rated_speed:300MB/s.

### FR 7 - View all User owned listings

| &darr; | &darr; |
| --- | --- |
| ID | **FR7** |
| TITLE | View all User owned listings |
| DESCRIPTION | View all listings the User owns as a list |
| RATIONALE | Allow User to view all of his/her listings |
| DEPENDENCY | FR1, FR5 |

### FR 8 - View a listing

| &darr; | &darr; |
| --- | --- |
| ID | **FR8** |
| TITLE | View a listing |
| DESCRIPTION | View a listing |
| RATIONALE | Allow User to view all listings |
| DEPENDENCY | FR1, FR5, FR6 |

Note: If listing belongs to User, display Edit/Update button.

### FR 9 - Update a listing

| &darr; | &darr; |
| --- | --- |
| ID | **FR9** |
| TITLE | Update a listing |
| DESCRIPTION | Update the details of a particular listing |
| RATIONALE | Allow User to view all listings |
| DEPENDENCY | FR1, FR5 |


### FR 10 - Add a phone number

| &darr; | &darr; |
| --- | --- |
| ID | **FR10** |
| TITLE | Add a phone number |
| DESCRIPTION | Add a phone number to the account for internal use and identity verification purposes |
| RATIONALE | If there are problems with the account, this contact can be used |
| DEPENDENCY | FR1, FR5 |

### FR 11 - Add an identity document

| &darr; | &darr; |
| --- | --- |
| ID | **FR11** |
| TITLE | Add an identity document |
| DESCRIPTION | Add an identity document (ID, driver's licence, healthcare card, passport, utility bill, etc) to the account for identity verification purposes |
| RATIONALE | Strong identity verification mechanis |
| DEPENDENCY | FR1, FR5 |

### FR 12 - Verify BARGAINER

| &darr; | &darr; |
| --- | --- |
| ID | **FR12** |
| TITLE | Verify the identity of a BARGAINER |
| DESCRIPTION | Verify the identity of a BARGAINER through phone, email, (travel documents, identity cards: similar to Paypal requirements), etc. Each level of verification comes with a badge and increases status |
| RATIONALE | For user security. Users should know when they are dealing with a legitimate and traceable person |
| DEPENDENCY | FR1, FR5 |

### FR 13 - Display User Profile

| &darr; | &darr; |
| --- | --- |
| ID | **FR13** |
| TITLE | Display Profile details |
| DESCRIPTION | Display User details \{name, phone number(s), address, email, profile picture\} |
| RATIONALE | For user reference and assurance |
| DEPENDENCY | FR1, FR5 |

### FR 14 - Update User Profile

| &darr; | &darr; |
| --- | --- |
| ID | **FR14** |
| TITLE | Update Profile details |
| DESCRIPTION | Update User details \{name(if unverified), nickname, phone number(s), address(primary, etc.), email, profile picture\} |
| RATIONALE | For user security. Users should know when they are dealing with a legitimate and traceable person |
| DEPENDENCY | FR1, FR5 |

Note: Data is never deleted or overwritten, only flagged as deleted, i.e. it no longer appears, but still exists.

### FR 15 - Display account information

| &darr; | &darr; |
| --- | --- |
| ID | **FR15** |
| TITLE | Display account information |
| DESCRIPTION | Display the following information \{account name, link to profile, link to BBCoin topup, link to user_listings, link to BBCoin transactions, BBCoin balance, badges, reputation(BARGAINER, EDITOR, TRANSLATOR, CATALOGUER) \} |
| RATIONALE | For user security. Users should know when they are dealing with a legitimate and traceable person |
| DEPENDENCY | FR1, FR5 |

### FR 16 - Top-up BBCoin balance

| &darr; | &darr; |
| --- | --- |
| ID | **FR16** |
| TITLE | Verify the identity of a BARGAINER |
| DESCRIPTION | Verify the identity of a BARGAINER through phone, email, (travel documents, identity cards: similar to Paypal requirements), etc. Each level of verification comes with a badge and increases status |
| RATIONALE | For user security. Users should know when they are dealing with a legitimate and traceable person |
| DEPENDENCY | FR1, FR5 |



Placeholder

| &darr; | &darr; |
| --- | --- |
| ID | **FR1** |
| TITLE | . |
| DESCRIPTION | . |
| RATIONALE | . |
| DEPENDENCY | . |
