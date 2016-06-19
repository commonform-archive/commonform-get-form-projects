```javascript
var getPublications = require('commonform-get-form-publications')
var assert = require('assert')
var responded = 0

var digest = (
  '9908d3adf96919e372eb05caaeedc5ba6' +
  'dc5db0ffcf23ee885d6b71dd1e76058' )

var publication = {
  digest: digest,
  publisher: 'ironsides',
  project: 'board-resolutions',
  edition: '1e4d' }

getPublications(digest, function(error, publications) {
  assert.deepEqual(publications, [ publication ])
  responded++ })

var allAs = 'a'.repeat(64)

getPublications(allAs, function(error, publications) {
  assert.deepEqual(publications, [ ])
  responded++ })

process.on('exit', function() {
  assert.equal(responded, 2)
  process.stdout.write('Tests passed.\n') })
```
