<html>
  <body>
  <h2>Consent-Receipt Demo site</h2>
  <div style="width:30em">
    <p>This website shows how a consent-receipt would work: when you
    <a href="signup.html">sign up</a> for this imaginary service, you
    agree to its terms of service, that is, you give your consent. Once
    you do this, a download link will appear where you can download a receipt
    of the consent you just gave. This is a machine-readable JSON-LD document,
    for you to keep, specifying what you agreed to and how to revoke the consent
    when you no longer do.</p>
  
    <p>It also contains a timestamp and a cryptographic signature (the signature is a fake one in this demo).
    The format is described on
    <a href="http://opennotice.org/spec/receipt-0.1">http://opennotice.org/spec/receipt-0.1</a>.</p>
    </div>
  </body>
  <script>
    function genReceipt() {
      return '{\n'
        + '  "@context": "http://opennotice.org/spec/receipt-0.1",\n'
        + '  "receipt":{\n'
        + '    "timestamp": ' + new Date().getTime() + ',\n'
        + '    "userId": "' + document.getElementById('email').value + '",\n'
        + '    "dialogUrl": "http://michielbdejong.github.io/consent-receipt/",\n'
        + '    "dnt": true,\n'
        + '    "revokeUrl": "http://michielbdejong.github.io/consent-receipt/quit",\n'
        + '    "policyUrls": [\n'
        + '      "http://michielbdejong.github.io/consent-receipt/terms",\n'
        + '      "http://michielbdejong.github.io/consent-receipt/privacy"\n'
        + '    ]\n'
        + '  },\n'
        + '  "jsonSignature": "tr0tberoijawflekrjg5wrgtbghdfgrt09rtgjw5tbrthe5ztntr"\n'
        + '}\n';
    }
    function go() {
      document.body.innerHTML = '<a href="data:,'+encodeURIComponent(genReceipt())
          +'" download>receipt</a>';
    }
  </script>
</html>
