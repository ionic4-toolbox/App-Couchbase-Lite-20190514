# Couchbase Lite Demo - Tea Cagtegories

This application performs full CRUD operations storing the data in a local database.

## Running the Application

In order to run this application, you need access to the Ionic Enterprise Couchbase Lite plugin. This plugin currently needs to be installed in `ionic-enterprise/couchbase-lite`. This needs to be installed before you perform the `npm install` step. In the future, this plugin will be included with the other Ionic Enterprise offerings and installed in a similar manner and accessed with your key.

If you do not have access to this plugin, please contact your account manager.

Here are the general steps required to run this application:

- clone the repo and change to its root directory
- install the Ionic Enterprise Couchbase Lite plugin as noted above
- `npm install`
- `npm run build`
- `ionic cordova platform add ios` (and/or android)
- `ionic cordova platform build ios` (and/or android)

At this point you should be able to sideload the application on a device or run it in an emulator and try it out.

## General Architecture

### Tea Categories Service

This services handles all of the CRUD operations. The service communicates with callers by passing the tea categories as regular typed TypeScript models rather than database objects. The reason for this is so the storage mechanism can easily be changed without affecting the callers.

### Pages

The pages know nothing about how the data is stored. The logic in the pages is only concerned with how the data is displayed and manipulated on the pages themselves. The end result being that if the way data is stored chanages the logic in the pages does not need to be touched.
