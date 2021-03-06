# Setup

In this portion of the tutorial, we will work on obtaining the following pieces of information:

  * Client ID
  * Client Secret
  * JWT private
  * JWT public
  * New AoC Integration

1. For spimlicity purposes, all files that will be required for this demo will be stored in `analytics-api-demo` directory. Go ahead and create that directory now. In terminal, complete the following:

    ```bash
    mkdir analytics-api-demo
    cd analytics-api-demo
    ```

    <div class="demo-image">
     <img src="images/1-create-demo-directory.png"/>
    </div>

1. Generate private and public keys

    ```bash
    ssh-keygen -t rsa -b 4096 -m PEM -f jwtRS256.key
    ```

    * when prompted, press enter twice to greate a key without a passphrase.

     <div class="demo-image">
       <img src="images/2-generate-keys.png"/>
     </div>

1. You should see the keys in the newly created files.

    <div class="demo-image">
     <img src="images/3-preview-private-key.png"/>
    </div>

1. Configure the public key for openssl

    ```bash
    openssl rsa -in jwtRS256.key -pubout -outform PEM -out jwtRS256.key.pub
    ```

     <div class="demo-image">
       <img src="images/4-configure-jwt-for-openssl.png"/>
     </div>

1. In the "Admin" app of AoC, create a new "Integration"

    <div class="demo-image">
     <img src="images/5-integrations-create-new.png"/>
    </div>

1. Here is what the "new" form will look like

    <div class="demo-image">
     <img src="images/6-new-form.png"/>
    </div>

1. Fill out form, for the purpose of the Analytics API, the "Redirect URIs" and "Orgins" can be any value. Click "Save".

    <div class="demo-image">
     <img src="images/7-new-form-filled-out.png"/>
    </div>

1. You should now be looking at your newly created Integration's "Profile".

    <div class="demo-image">
     <img src="images/8-profile-details.png"/>
    </div>

1. Click on the submenu "JSON Web Token Auth".

    <div class="demo-image">
     <img src="images/9-jwt-landing.png"/>
    </div>

1. Select the check-box for "Enable JWT grant type".

    <div class="demo-image">
     <img src="images/10-jwt-selections.png"/>
    </div>

1. From the drop-down menu, select, "User-specific keys and global key".

    <div class="demo-image">
     <img src="images/11-jwt-selections-continued.png"/>
    </div>

1. Confirm that you would like to permit global keys. Click "Yes".

    <div class="demo-image">
     <img src="images/12-allow-gloabl-keys.png"/>
    </div>

1. Add your public JWT (generated in step 3) to the field titled "Public Key (PEM Format)". Click "Save".

    <div class="demo-image">
     <img src="images/13-copy-public-key.png"/>
    </div>

1. In terminal, create an empty `.config.yml` file.

    ```bash
    touch config.yml
    ```

     <div class="demo-image">
       <img src="images/14-create-empty-config.png"/>
     </div>

1. In AoC app, use the submenu to visit your integration "Profile". Use the keys that I have listed in the `config.yml` file; however, update the values with information that is specific to you.

    <div class="demo-image">
     <img src="images/15-add-config-data.png"/>
    </div>

1. Visit [API Requests](./analytics-api.md) to learn about making requests to the Analytics API.
