## Fosdick
## Quickbooks
## Mandril

* Replace with Mandril Rails gem.
* Wire each one up to their corresponding Mandril templates.

## MDS

* Standardish API. Will be able to test using VCR style cassettes recordings.
* Uses XML To send the `Order` object with included `Lines`.
 * Very familiar to the xml object built with Fosdick.
* Shipping and billing info need to be coerced into correct xml nodes.
* Special totals section also required for the XML sent.
* No need to worry about split shipments.
* No need to worry about sending more than one 'box' per shipment.