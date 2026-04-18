XSS Context Guide :

Understanding the context where your input is reflected is crucial for successful XSS exploitation.

1.HTML Context:

    Input is placed directly into the HTML body. 
    Example: <div>USER_INPUT</div>
    Payload: <script> alert(1) </script> why? You need to break out of the attribute string(") and the tag(>) to start a new script tag. 
    Alternative: " onmouseover=alert(1)autofocus=" (Uses event handler without breaking the tag).

2.Attribute Context:

    Input is placed inide an HTML attribute.
    Example: <input value="USER_INPUT>
    Payload: "><script>alert(1)</script> Why?
    You need to break out of the attribute string (") and the tag(<) to start a new script tag.
    Alternative: "onmoueover=alert(1)autofocus=" (Uses event handler without breaking the tag).
