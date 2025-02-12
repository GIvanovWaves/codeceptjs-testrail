##### Testrail
 
  Enables Testrail integration.

##### Requirement

  To use this custom plugin
  ```sh
  npm i codeceptjs-testrail --save-dev
  ```

  **Note:** you should include the test case id to make it works, otherwise, this plugin has no clue which case id to be added to test run on Testrail.

  An example:
  ```js
  Scenario('Search function is displayed @C12345', (I, homePage) => {
    I.seeElement(homePage.searchTextbox);
    I.seeElement(homePage.searchButton);
  });
  ```
 
##### Configuration
 
   Add this plugin to config file:
  
   ```js
   plugins: {
       testrail: {
          require: 'codeceptjs-testrail',
          host: 'https://peternguyentr.testrail.io',
          user: 'username',
          password: 'password or api key',
          suiteId: 1,
          projectId: 1,
          runName: 'Custom run name',
          enabled: true
    }
   }
   ```
  
   Possible config options:
  
   `suiteId`: when your project is not under the single-suite mode, `suiteId` is needed. When you don't provide the `suiteId`, the first `suiteId` will be used as default.  
   `projectId` (Required): The project Id which is from the Testrail. This should be provided to make this plugin works
   `runName` (Optional): your desired test run name. If you done provide this test run name, default test run name is as `This is a new test run on ${dd/mm/yyy}` which is current day.