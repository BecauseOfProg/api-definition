<div align="center">
  <img src="https://cdn.becauseofprog.fr/v2/sites/becauseofprog.fr/assets/logos/bop.min.svg" alt="Logo BecauseOfProg"  width="150"/>
  <h1>BecauseOfProg's API</h1>
  <h3>Fetch all kind of informations related to the BecauseOfprog</h3>
</div>

Welcome on the BecauseOfProg's API ! Here, you can fetch data related to us, for example blog posts !

First of all, you need a URL in order to access it. The root URL for the API is `https://api.becauseofprog.fr`. This URL is followed by the version of this format : `v{number}`. You can find versions below :

| Version | Status    |
| ------- | --------- |
| 1       | Available |

Every response is in JSON format, and has in its body a `code` which is `1` or `0`, depending on the request's success or not, and all requested fields.