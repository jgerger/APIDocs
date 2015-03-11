{{{
  "title": "UpdatePublicIPAddress",
  "date": "5-1-2013",
  "author": "Peter Kowalczyk",
  "attachments": []
}}}

Configures firewall settings on a public IP Address.

## URL

    REST: https://api.tier3.com/REST/Network/UpdatePublicIPAddress/<format>
    SOAP: https://api.tier3.com/SOAP/Network.asmx?op=UpdatePublicIPAddress

## Request

### Attributes

<table>
  <thead>
    <tr>
      <th>Name</th>
      <th>Type</th>
      <th>Description</th>
      <th>Req.</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>AccountAlias</td>
      <td>&nbsp;String</td>
      <td>
        <p>&nbsp;The alias of the account that owns the server.&nbsp; If not provided it will assume the Account the API user is mapped to.&nbsp; Providing this value gives you the ability to manage servers in your sub accounts.</p>
      </td>
      <td>&nbsp;No</td>
    </tr>
    <tr>
      <td>ServerName</td>
      <td>String</td>
      <td>
        <p>The name of the server. &nbsp;</p>
      </td>
      <td>Yes</td>
    </tr>
    <tr>
      <td>PublicIPAddress</td>
      <td>String</td>
      <td>
        <p>The public, mapped IP to manage.</p>
      </td>
      <td>
        <p>Yes</p>
      </td>
    </tr>
    <tr>
      <td>AllowHTTP</td>
      <td>Boolean</td>
      <td>
        <p>&nbsp;The public IP mapping will allow&nbsp;HTTP requests.</p>
      </td>
      <td>
        <p>&nbsp;No</p>
      </td>
    </tr>
    <tr>
      <td>AllowHTTPonPort8080</td>
      <td>Boolean</td>
      <td>
        <p>&nbsp;The public IP mapping will allow&nbsp;HTTP requests on port 8080.</p>
      </td>
      <td>
        <p>&nbsp;No</p>
      </td>
    </tr>
    <tr>
      <td>AllowHTTPS</td>
      <td>Boolean</td>
      <td>
        <p>&nbsp;The public IP mapping will allow&nbsp;HTTPS requests.</p>
      </td>
      <td>
        <p>&nbsp;No</p>
      </td>
    </tr>
    <tr>
      <td>AllowFTP</td>
      <td>Boolean</td>
      <td>
        <p>&nbsp;The public IP mapping will allow&nbsp;FTP requests.</p>
      </td>
      <td>
        <p>&nbsp;No</p>
      </td>
    </tr>
    <tr>
      <td>AllowFTPS</td>
      <td>Boolean</td>
      <td>
        <p>&nbsp;The public IP mapping will allow&nbsp;FTPS requests.</p>
      </td>
      <td>
        <p>&nbsp;No</p>
      </td>
    </tr>
    <tr>
      <td>AllowSFTP</td>
      <td>Boolean</td>
      <td>
        <p>&nbsp;The public IP mapping will allow&nbsp;SFTP requests.</p>
      </td>
      <td>
        <p>&nbsp;No</p>
      </td>
    </tr>
    <tr>
      <td>AllowSSH</td>
      <td>Boolean</td>
      <td>
        <p>&nbsp;The public IP mapping will allow&nbsp;SSH requests.</p>
      </td>
      <td>
        <p>&nbsp;No</p>
      </td>
    </tr>
    <tr>
      <td>AllowRDP</td>
      <td>Boolean</td>
      <td>
        <p>&nbsp;The public IP mapping will allow&nbsp;RDP requests.</p>
      </td>
      <td>
        <p>&nbsp;No</p>
      </td>
    </tr>
  </tbody>
</table>

### Examples

#### JSON

    {

      "AccountAlias": "SUB1",

      "ServerName": "WA1T3NWEB01",

      "PublicIPAddress": "1.1.1.1",

      "AllowHTTP": true,

      "AllowHTTPonPort8080": false,

      "AllowHTTPS": false,

      "AllowFTP": false,

      "AllowFTPS": false,

      "AllowSFTP": false,

      "AllowSSH": false,

      "AllowRDP": false

    }

#### XML

    <UpdateIPAddressRequest>

        <AccountAlias>SUB1</AccountAlias>

        <ServerName>WA1T3NWEB01</ServerName>

        <PublicIPAddress>1.1.1.1</PublicIPAddress>

        <AllowHTTP>true</AllowHTTP>

        <AllowHTTPonPort8080>false</AllowHTTPonPort8080>

        <AllowHTTPS>false</AllowHTTPS>

        <AllowFTP>false</AllowFTP>

        <AllowFTPS>false</AllowFTPS>

        <AllowSFTP>false</AllowSFTP>

        <AllowSSH>false</AllowSSH>

        <AllowRDP>false</AllowRDP>

    </UpdateIPAddressRequest>

## Response

### Attributes

<table>
  <thead>
    <tr>
      <th>Name</th>
      <th>Type</th>
      <th>Description</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>Success</td>
      <td>Boolean</td>
      <td>True if the request was successful, otherwise False.</td>
    </tr>
    <tr>
      <td>Message</td>
      <td>String</td>
      <td>A description of the result. The contents of this field does not contain any actionable information, it is purely intended to provide a human readable description of the result.</td>
    </tr>
    <tr>
      <td>StatusCode</td>
      <td>Int</td>
      <td>This value will help to identify any errors which were encountered while processing the request. The value of '0' indicates success, all non-zero StatusCodes indicate an error state.</td>
    </tr>
    <tr>
      <td>RequestID</td>
      <td>Int</td>
      <td>
        <p>
          <br />The ID of the Blueprint Reques submitted to perform this operation.</p>
        <p>You can check the status of this operation by calling the GetRequestStatus method on the Bllueprint API.</p>
      </td>
    </tr>
  </tbody>
</table>

### Examples

#### JSON

    {

      "Success": true,

      "Message": "Success",

      "StatusCode": 0,

      "RequestID": 1

    }

#### XML

    <QueuedItemResponse Success="true" Message="Success" StatusCode="0" RequestID="1" />

### Status Codes

<table>
  <thead>
    <tr>
      <th>Status Code</th>
      <th>Description</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>0</td>
      <td>Request was successfully processed</td>
    </tr>
    <tr>
      <td>2</td>
      <td>Unknown Error - An application error occurred processing your request, contact Tier3 support to resolve the issue.</td>
    </tr>
    <tr>
      <td>3</td>
      <td>Invalid Request Format. This value indicates that the XML or JSON requests do not match the expected format.</td>
    </tr>
    <tr>
      <td>5</td>
      <td>Resource Not Found.&nbsp;&nbsp;A Server with the specified Name cannot be found.&nbsp;</td>
    </tr>
    <tr>
      <td>6</td>
      <td>Invalid Operation.&nbsp;&nbsp;Server must be in an active state.</td>
    </tr>
    <tr>
      <td>100</td>
      <td>Authentication Failed - You must logon to the API prior to calling this method.</td>
    </tr>
    <tr>
      <td>101</td>
      <td>Access Denied - Your API user does not have access to the account specified.</td>
    </tr>
    <tr>
      <td>506</td>
      <td>Server Name Required.</td>
    </tr>
    <tr>
      <td>1511</td>
      <td>Public IP Address Required.</td>
    </tr>
    <tr>
      <td>1000</td>
      <td>The&nbsp;Public IP Address provided is not&nbsp;configured on&nbsp;the Server.</td>
    </tr>
  </tbody>
</table>