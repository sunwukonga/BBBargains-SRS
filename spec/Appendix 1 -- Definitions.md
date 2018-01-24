# A. Appendix 1

## Definitions, Acronyms, and Abbreviations

### Definitions

 
<table>
<colgroup>
<col style="width: 27px">
<col style="width: 27px">
<col style="width: 287">
</colgroup>
  <tr>
    <th class="show">**Term**</th>
    <th class="show" colspan="2">**Definition**</th>
  </tr>
  <tr>
    <td>**User**</td>
    <td colspan="2">Someone who wants to buy/sell, exchange, donate/receive baby goods and services, logged or unlogged (anonymous). User can fulfil zero or more of the following roles: BARGAINER, TRANSLATOR, EDITOR, or ARRANGER.</td>
  </tr>
  <tr>
    <td rowspan="4">*User Roles*</td>
    <td>BARGAINER</td>
    <td>A User that buys/sells, exchanges, donates/receives baby goods and/or services.</td>
  </tr>
  <tr>
    <td>TRANSLATOR</td>
    <td>A User that translates content from English into a targeted language or languages.</td>
  </tr>
  <tr>
    <td>EDITOR</td>
    <td>A User that edits the listing content of another User, i.e. to correct a spelling mistake or product misrepresentation, or a similar mistake in app content.</td>
  </tr>
  <tr>
    <td>CATALOGUER</td>
    <td>A User that recognises duplicate categories, better categorisation, duplicate product templates, etc., and proposes fixes.</td>
  </tr>
  <tr>
    <td>**PLanguage**</td>
    <td colspan="2">A keyword-driven language that allows measurable, testable quality requirements to be written. [Read this reference](http://www.geocities.ws/g/i/gillani/SE'2 Full Lectures/ASE -  Planguage Quantifying Quality Requirements.pdf).</td>
  </tr>
  <tr>
    <td rowspan="14">*PLanguage Keywords*</td>
    <td>TAG</td>
    <td>A unique, persistent identifier.</td>
  </tr>
  <tr>
    <td>GIST</td>
    <td>A short, simple description of the concept contained in the Planguage statement.</td>
  </tr>
  <tr>
    <td>STAKEHOLDER</td>
    <td>A party materially affected by the requirement.</td>
  </tr>
  <tr>
    <td>SCALE</td>
    <td>The scale of measure used to quantify the statement.</td>
  </tr>
  <tr>
    <td>METER</td>
    <td>The process or device used to establish location on a SCALE.</td>
  </tr>
  <tr>
    <td>MUST</td>
    <td>The minimum level required to avoid failure.</td>
  </tr>
  <tr>
    <td>PLAN</td>
    <td>The level at which good success can be claimed.</td>
  </tr>
  <tr>
    <td>STRETCH</td>
    <td>A stretch goal if everything goes perfectly.</td>
  </tr>
  <tr>
    <td>WISH</td>
    <td>A desirable level of achievement that may not be attainable.</td>
  </tr>
  <tr>
    <td>PAST</td>
    <td>An expression of previous results for comparison.</td>
  </tr>
  <tr>
    <td>TREND</td>
    <td>An historical range or extrapolation of data.</td>
  </tr>
  <tr>
    <td>RECORD</td>
    <td>The best-known achievement.</td>
  </tr>
  <tr>
    <td>DEFINED</td>
    <td>The official definition of a term.</td>
  </tr>
  <tr>
    <td>AUTHORITY</td>
    <td>The person, group, or level of authorization.</td>
  </tr>
  <tr>
    <td rowspan="14">*Sub-keywords on* METER</td>
    <td>METHOD</td>
    <td>The method for measuring to determine a point on the Scale.</td>
  </tr>
  <tr>
    <td>FREQUENCY</td>
    <td>The frequency at which measurements will be taken.</td>
  </tr>
  <tr>
    <td>SOURCE</td>
    <td>The people or department responsible for making the measurement.</td>
  </tr>
  <tr>
    <td>REPORT</td>
    <td>Where and when the measurement is to be reported.</td>
  </tr>
</table>

### Abbreviations

 
<table>
<colgroup>
<col style="width: 27px">
<col style="width: 27px">
<col style="width: 287">
</colgroup>
  <tr>
    <th class="show">**Abbreviation**</th>
    <th class="show">**Original**</th>
  </tr>
  <tr>
    <td>**DESC**</td>
    <td>DESCRIPTION</td>
  </tr>
  <tr>
    <td>**RAT**</td>
    <td>RATIONALE</td>
  </tr>
  <tr>
    <td>**DEP**</td>
    <td>DEPENDENCY</td>
  </tr>
</table>

 
![How spec-md works](http://g.gravizo.com/svg?
  digraph specmd {
    markdown [shape=box];
    ast [shape=box];
    html [shape=box];
    markdown -> parse [weight=8];
    parse -> ast;
    ast -> print;
    edge [color=red];
    print -> html;
  }
)
