{{{
  "title": "Get Blueprint Parameters",
  "date": "9-15-2014",
  "author": "Troy Schneringer",
  "attachments": []
}}}

<div>
  <div>
    GetBlueprintParameters
    <p>Gets a the full list of parameters that are required to deploy a Blueprint.</p>
    URL
    <pre>REST: <code>https://api.tier3.com/REST/Blueprint/GetBlueprintParameters/&lt;format&gt;</code><br />SOAP: <code>https://api.tier3.com/SOAP/Blueprints.asmx?op=GetBlueprintParamatersResponseMsg</code></pre> Request
    <h3>Attributes</h3>
    <table>
      <tbody>
        <tr>
          <td><strong>Name</strong>
          </td>
          <td><strong>Type</strong>
          </td>
          <td><strong>Description</strong>
          </td>
          <td><strong>Required</strong>
          </td>
        </tr>
        <tr>
          <td>ID</td>
          <td>Int</td>
          <td>
            <p>The ID of the Blueprint to retrieve parameters for.</p>
          </td>
          <td>
            <p>Yes</p>
          </td>
        </tr>
      </tbody>
    </table>
    <h3>Examples</h3>
    <h4>JSON</h4>
    <pre>{ "ID":1 }</pre>
    <h4>XML</h4>
    <pre>&lt;BlueprintRequest&gt;<br />    &lt;ID&gt;1&lt;/ID&gt;<br />&lt;/BlueprintRequest&gt;&nbsp;</pre> Response
    <h3>Attributes</h3>
    <table>
      <tbody>
        <tr>
          <td><strong>Name</strong>
          </td>
          <td><strong>Type</strong>
          </td>
          <td><strong>Description</strong>
          </td>
        </tr>
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
          <td>Parameters</td>
          <td>List</td>
          <td>A list of the parameters required to deploy the Blueprint (see below)</td>
        </tr>
      </tbody>
    </table>
    <h3>Parameter Attributes</h3>
    <table>
      <tbody>
        <tr>
          <td><strong>Name</strong>
          </td>
          <td><strong>Type</strong>
          </td>
          <td><strong>Description</strong>
          </td>
        </tr>
        <tr>
          <td>Name</td>
          <td>String</td>
          <td>
            <p>The name of the Parameter.</p>
          </td>
        </tr>
        <tr>
          <td>Options</td>
          <td>List</td>
          <td>
            <p>A list of options to choose from if the Parameter is an Option or MultiSelect type.</p>
            <p>Each option has 2 attributes:
              <br />Name = The name of the option
              <br />Value = The value of the option&nbsp;</p>
          </td>
        </tr>
        <tr>
          <td>Regex</td>
          <td>String</td>
          <td>
            <p>A regular expression defining any additional validation that the Parameter value must pass.&nbsp;</p>
            <p>This value is supplied by the Blueprint author.</p>
          </td>
        </tr>
        <tr>
          <td>Type</td>
          <td>
            <p>JSON: Int
              <br />XML: String&nbsp;</p>
          </td>
          <td>
            <p>The data type of the Parameter</p>
            <p>1/Network = &nbsp;internal name of an existing network
              <br />2/Numeric = numeric value
              <br />3/Option = constrained to only one of the listed options
              <br />4/Password = password value
              <br />5/Server = name of an existing server
              <br />6/ServerIP = IP address of an existing server
              <br />7/String = string value
              <br />8/MultiSelect = value constrained to one or more of the listed options</p>
          </td>
        </tr>
      </tbody>
    </table>
    <h3>Examples</h3>
    <h4>JSON</h4>
    <pre>{<br />    "ID":1,<br />    "Parameters":[<br />        {<br />            "Name":"T3.ScriptTask.Parameter01",<br />            "Regex":null,<br />            "Type":7,<br />            "Options":[]<br />        },

        {<br />            "Name":"T3.ScriptTask.Parameter02",<br />            "Regex":null,<br />            "Type":3,<br />            "Options":[<br />                {"Name":"Option 1","Value":"1"},<br />                {"Name":"Option 2","Value":"2"}<br />            ]<br />        } <br />    ],<br />    "Success":true,<br />    "Message":"Success",<br />    "StatusCode":0<br />}</pre>
    <h4>XML</h4>
    <pre>&lt;GetBlueprintParamatersResponse Success="true" Message="Success" StatusCode="0"&gt;<br />    &lt;ID&gt;46&lt;/ID&gt;<br />    &lt;Parameters&gt;<br />        &lt;Parameter Name="T3.ScriptTask.Parameter01" Type="String" /&gt;

        &lt;Parameter Name="T3.ScriptTask.Parameter02" Type="Option"&gt;<br />            &lt;Option Name="Option 1" Value="1"/&gt;<br />            &lt;Option Name="Option 2" Value="1"/&gt;<br />        &lt;/Parameter&gt;<br />    &lt;/Parameters&gt;<br />&lt;/GetBlueprintParamatersResponse&gt;</pre>
    <h3>Status Codes</h3>
    <table>
      <tbody>
        <tr>
          <td><strong>Status Code</strong>
          </td>
          <td><strong>Description</strong>
          </td>
        </tr>
        <tr>
          <td>0</td>
          <td>Request was successfully processed</td>
        </tr>
        <tr>
          <td>2</td>
          <td>Unknown Error. &nbsp;An application error occurred processing your request, contact Tier3 support to resolve the issue.</td>
        </tr>
        <tr>
          <td>3</td>
          <td>Invalid Request Format. This value indicates that the XML or JSON requests do not match the expected format.</td>
        </tr>
        <tr>
          <td>5</td>
          <td>Resource Not Found. &nbsp;A Blueprint with the specified ID cannot be found.</td>
        </tr>
        <tr>
          <td>100</td>
          <td>Authentication Failed. &nbsp;You must logon to the API prior to calling this method.</td>
        </tr>
      </tbody>
    </table>
  </div>
</div>