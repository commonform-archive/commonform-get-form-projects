```javascript
var getProjects = require('commonform-get-form-projects')
var assert = require('assert')

var digest = (
  '9908d3adf96919e372eb05caaeedc5ba6' +
  'dc5db0ffcf23ee885d6b71dd1e76058' )

var project = {
  form: digest,
  publisher: 'ironsides',
  project: 'board-resolutions',
  edition: '1e4d' }

getProjects(digest, function(error, projects) {
  assert.deepEqual(projects, [ project ]) })
```
