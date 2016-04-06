# quorra-prebuild
Prebuilds @tanepiper/quorra. It should work exacly as the original.
Just a workaround to fix https://github.com/tanepiper/quorra/issues/2

## Install
`npm install --save ken210/quorra-prebuild`

## Usage
```
server.register([{
  register: require('quorra')
}], (error) => {
  if (error) {
    throw error;
  }

  server.route({
    method: 'GET',
    path: '/{route*}',
    handler: {
      react: {
        relativeTo: `${__dirname}/app`,
        router: 'routes.js',
        layout: 'layout.jsx' || 'myLayoutMethod',
        props: {
          '/': 'myIndexMethod',
          '/about': 'myAboutMethod'
        }
      }
    }
  });
});
```