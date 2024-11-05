<h1> Fiori </h1>

- [Expose Z* Program Or Standard Transaction to Fiori](#Expose-Z*-Program-Or-Standard-Transaction-to-Fiori)<br>
  - [Create Semantic Object](#Creaete-Semantic-Object)
  - [Create A Customazing Transport Request (Optional)](#Create-A-Customazing-Transport-Request)
  - [Create Tile](#Create-App-Tile)
  - [Create Business Catalog](#Create-Business-Catalog)
  - [Create Business Catalog Tile](#Create-Business-Catalog-Tile)
  - [Create Business Catalog Target Mapping](#Create-Business-Catalog-Target-Mapping)
  - [Create Business Group](#Create-Business-Group)
  - [Create Role](#Create-Role)
  - [Custom Tile Translation](#Custom-Tile-Translation)
- [Expose Standard App to Fiori (Techical Catalog)](#Expose-Standard-App-to-Fiori)
- [Authorization Issues](#Authorization-Issues)
- [Copy Standard Role to Z*](#Copy-Standard-Role-to-Z*)
- [Fiori T-Codes](#Fiori-T-Codes)
  
# Expose Z* Program Or Standard Transaction to Fiori

 ## Create Semantic Object
  T-Code - To define custom Semantic objects : `/N/UI2/SEMOBJ`<BR>
  Press Change and then New Entries <BR>
  Preferably use the Title of the Program to be exposed <BR>
  > [!IMPORTANT]
  > You need a Workbench Request to Transport Semantic Objects<BR>
  
 ## Create A Customazing Transport Request 
  Go to `SE10` and create a Customazing Request if you dont already have one.
 ## Create App Tile
   In Order to Expose the Program we need a Business Catalog and a Business Group <BR>
   T-Code - Launch SAP FIORI Launchpad designer for customization ( client-specific ) : `/N/UI2/FLPD_CUST`<BR>
   In the Upper Left Corner we can choose Among Catalog and Group <BR>
   <img width="250" alt="image" src="https://github.com/SpyrosEvg/Abap_Code/assets/39948427/31ce49c9-ca95-401a-a999-4bd96bf4674c"> <br>
   > [!NOTE]
   > <B> - TILE </B>  <br>
   > Tile is the island that you saw in the Fiori Launchpad  <br>
   > Tile and Target Mapping is connecting through the Semantic Object and the Action <br>
   > Semanctic Object and Action must be a unique compination <br>
   > The original tile exists in a business catalog (You can copy by reference to another business catalog) <br>
   > <B> - GROUP </B> <br>
   > Groups exists in a Business Groups <br>
   > Groups contains tiles (can contain tiles from different business catalog) <br>
   > In Order the Tile to be visible in the Fiori Launchpad Home page must be placed in a group <br>
   
  ## Creating Business Catalog
   > [!IMPORTANT]
   > In the Top Rignt there is a Gear <img width="35" alt="image" src="https://github.com/SpyrosEvg/Abap_Code/assets/39948427/c7a368f8-afc1-495a-b9e1-12d1f6b02055"> <br>
   > Uncheck the None(Local Object) and enter the Customazing TR

  ## Create Business Catalog Tile
  <img width="250" alt="image" src="https://github.com/SpyrosEvg/Abap_Code/assets/39948427/2e748812-d821-4c72-8c05-80bdcb11cdbf"> <br>
  In Bottom Left there is a Plus Sign <img width="27" alt="image" src="https://github.com/SpyrosEvg/Abap_Code/assets/39948427/bcef5d37-640c-4095-9204-fd0f6a46d2b6"> <br>
  Fill the Title and ID <br>
  ![image](https://github.com/user-attachments/assets/784006d1-3876-4b68-8ce3-065995bba519) <br>
  >[!NOTE]
  ><i>ID</i> must start with Z* and BC* Example : Z_BC_TEST) <br>
  >Its Case-sensitive

  ##
  Then Select the Tile with the plus sigh : <br>
  <img width="94" alt="image" src="https://github.com/SpyrosEvg/Abap_Code/assets/39948427/3017e2ce-f66d-4b68-894f-20dfb875133d"> <br>
  ##
  Choose the <i>App Launcher - Static</i>: <br>
  <img width="150" alt="image" src="https://github.com/SpyrosEvg/Abap_Code/assets/39948427/87f97b73-fcf4-4068-bf72-d7341e4f468d"> <br>
  ##
  Here this screen will pop up : <br>
  <img width="950" alt="image" src="https://github.com/SpyrosEvg/Abap_Code/assets/39948427/5f2fed22-8116-469c-8b6f-eedf8938e021"> <br>
  Creating Tile Screen : Lets break it down <br>
  <ul>
    <li> <b>Title</b>: The title of the Tile</li>
    <li> <b>Subtitle</b>: The Subtitle of the Tile </li>
    <li> <b>Keywords</b>: Key word for search ( Preferbly enter the t-code )</li>
    <li> <b>Semantic Object</b> : Enter the Semantic Object created in <i> Create Semantic Object </i> Section </li>
    <li> <b>Action</b>: Enter <i>manage</i> </li>
    <li> And then save </li>
  </ul>
  
  >[!NOTE] 
  >If you need to Delete a Business Catalog Tile just drag the Tile and this will pop up : <br>
  ><img width="62" alt="image" src="https://github.com/SpyrosEvg/Abap_Code/assets/39948427/da0745c0-507c-4587-8138-222a40facec5"> <br>
  ##
  ## Create Business Catalog Target Mapping
  <img width="250" alt="image" src="https://github.com/user-attachments/assets/df6c55fe-552b-4716-a010-df3abf41c6e4"> <br>
  ##
  In the bottom center-right screen you will see <i>Create Targer Mapping</i> <br>
  <img width="250" alt="image" src="https://github.com/SpyrosEvg/Abap_Code/assets/39948427/ae6b9457-3b60-4b12-ac71-fe835df4ea62"> <br>
  ##
  Here this screen will pop up : <br>
  <img width="959" alt="image" src="https://github.com/SpyrosEvg/Abap_Code/assets/39948427/533c86fc-38a5-4e5f-9318-b0f6113a5dd6"> <br>
  Creating Target Mapping Screen : Lets break it down <br>
   <ul>
    <li> <b>Semantic Object</b> : Enter the same Semantic Object entered in above step </li>
    <li> <b>Action</b>: Enter <i>manage</i> </li>
    <li> <b>Application Type</b>: Select <i>Transaction</i> </li>
    <li> <b>Title</b>: The title of the Program </li>
    <li> <b>Transaction</b>: The Transaction Code you need to expose </li>
    <li>And then save </li>
  </ul>
  
   ## Create Business Group 
  In Bottom Left there is a Plus Sign (Same as Business Catalog )<img width="27" alt="image" src="https://github.com/SpyrosEvg/Abap_Code/assets/39948427/bcef5d37-640c-4095-9204-fd0f6a46d2b6"> <br>
  ##
  Fill the Title and ID  <br>
  <img width="250" alt="image" src="https://github.com/SpyrosEvg/Abap_Code/assets/39948427/ad9a09fd-ef7b-4205-af4e-3e84b12667c3"> <br>
  >[!NOTE]
  > <i>ID</i> must start with Z* and BG* Example : Z_BG_TEST
  > Its Case-sensitive

  ##
  Then Select <i>Show as Tile</i>: <br> 
  <img width="110" alt="image" src="https://github.com/SpyrosEvg/Abap_Code/assets/39948427/36951f8e-e3d4-40ce-a8b3-e9dc4043ca45"> <br>
  ##
  After that you will need to select the Business Catalog that you created with F4 <br>
  <img width="250" alt="image" src="https://github.com/SpyrosEvg/Abap_Code/assets/39948427/0d0bb532-f8d2-44b4-8440-192412a6f8bd"> <br>
  ##
  And select the plus :heavy_plus_sign: in the tiles you want to put in the Busicess Group <br>
  >When it becomes green the tile is inserted in Business Group <br>
  
  <img width="250" alt="image" src="https://github.com/SpyrosEvg/Abap_Code/assets/39948427/d1953492-cc22-454a-a465-7627de9140a6"> <br>
  >[!NOTE] 
  >If you want to delete a tile from a group drag the tile and this pop up will show in buttom right <br>
  ><img width="106" alt="image" src="https://github.com/SpyrosEvg/Abap_Code/assets/39948427/52465577-b36a-4c02-8f27-2b068c3a728d"> <br>
    
 ## Create Role
 >There are two Roles :
 >1. Single Role
 >   In Signle roles you can instert multiple Business Catalogs and Business Groups and GUI Transaction and much more.
 >   Also, you can define the authorization that role has.
 >2. Composite Role
 >   In Composite Role you can have multiple Single Roles from grouping for example Per Module or Per Company Code
 ##
 First go to the T-Code Role Maintenance : `PFCG` <br>
 Enter the name of the role then select <i>Single Role</i> or <i>Composite Role</i> depending your needs <br>
 <img width="600" alt="image" src="https://github.com/SpyrosEvg/Abap_Code/assets/39948427/e7ffcdea-7173-48e1-8ab1-0b218e2366b9"><br>
 ##
 After that you need to put your Catalog and Group that you create into the role: <br>
 Select The Arrow in <i>Transaction</i> then select <i> SAP Fiori Launchpad </i> and then <i>Lanchpad Catalog / Lanchpad Group</i>
 <img width="400" alt="image" src="https://github.com/SpyrosEvg/Abap_Code/assets/39948427/95a9dbb4-588e-4fe7-8928-1859870b621a"><br>
 Finally, enter the ID of the Catalog and Group that you created respectivly
 > Its Case-sensitive
 ##
 Next you need to Generate the Authorizations:<br>
 In the Authorization tab <br>
 <img width="378" alt="image" src="https://github.com/SpyrosEvg/Abap_Code/assets/39948427/b65dff96-bdca-4b81-93c7-97e2f105848a"><br>
 So go to <i>Edit Authorization Data and Generate Profiles</i> and press <i>Change Authorization Data </i>

 ##
 In the Authorization Data <br>
 if there is an Organizational Data this screen will pop up <br>
 <img width="426" alt="image" src="https://github.com/SpyrosEvg/Abap_Code/assets/39948427/42504113-c4a5-4cbd-b66a-e34e2bc1fa37"><br>
 The Organizational Data is like Global Variables for Authorazation Objects and here you can specify Company Code , Purchasing Group etc etc.
 ##
 <i>Generate</i> <br>
 <img width="30" alt="image" src="https://github.com/SpyrosEvg/Abap_Code/assets/39948427/468b3be5-13f5-47d2-854d-af68e2a22827"> <br>
 ##
 Also in the <i>Users</i> Tab you can put the Users you want to use this role
 ##
 >[!NOTE]
 > In order to tranport a role, in the initial screen of the transaction there a
 > <img width="600" alt="image" src="https://github.com/user-attachments/assets/8a0db830-fd01-4084-a848-e782cbc573e3"><br>
 > Also, you need a Customazing Request for the transport.
 > If you make any changes in Business Catalog you need to remove and enter it again <br>
 > and you need to generate the Authorizations again
 
 ## Custom Tile Translation 
 First you need to go in Transaction Code `/UI2/FLP`
 and enter the Catalog of the tiles that need to be translated
 <img width="350" alt="image" src="https://github.com/user-attachments/assets/acacbd81-6c45-4b4f-99ab-84506de6ddf4"> <br>
 Then in the second Screen Select the tile you want to translate <br>
 <img width="550" alt="image" src="https://github.com/user-attachments/assets/67d73131-1df8-48eb-a854-3c047296948f"> <br>
 After that, another Screen will appear <br>
 <img width="550" alt="image" src="https://github.com/user-attachments/assets/81ec6bad-4682-4faa-bb87-d70d66b836a4"> <br>
 Here you have 2 <i>Config IDs</i> , one for Tile and one for Target Mapping (TM). <br>
 You need to Translate Both. <br>
 Take the Config IDs and go to Transaction Code `SE63` -> <i>Short Text</i> -> <i>00 Meta Objects</i> -> <i>TABL Tables</i> <br>
 <img width="550" alt="image" src="https://github.com/user-attachments/assets/92b1fc80-d591-4742-a0cc-16067963b7f6"> <br>
 Here put in the Object Name <i>* WDY_CONF_USERT2 *</i> (Without Spaces in *), select the translation languages, press enter and put the Config ID<br>
 <img width="550" alt="image" src="https://github.com/user-attachments/assets/e697b5a8-7cb3-4484-b458-3d9ad12300b6"> <br>
 Do the Transaltion that you want and Save it. <br>

 After this in order to Transport the Transaltions go to Transaction Code `SLXT` <br>
 Select the Target Language of the translation that you made in the previous Step, <br>
 enter the Processing Date of the translation , <br>
 enter in the fields <i>Object Type = * </i>  and <i>Object Processor = Your Username </i>
 and Execute.

 A Transport Request will appear in the `SE10`.

 > [!IMPORTANT]
 > If the Translation does not appear you need to Clear the Back-End Cache , <br>
 > To Do this, call transaction SE38 and run the report /UI2/INVALIDATE_GLOBAL_CACHES in execution mode <br>

 >Reference Document : https://help.sap.com/docs/UI_ADD-ON_FOR_SAP_NETWEAVER_20/17ae0e97e0fc424a9c368f350c0ba6bd/4c9eb085d3884bdca468d7ec284be2e2.html

 # Expose Standard App to Fiori
 Same Times SAP provides the solution to export Standard Transaction in Fiori.<br>
 When you want to Export Standard Transaction into Fiori the First thing to do is to go in [Fiori Libraty](https://fioriappslibrary.hana.ondemand.com/sap/fix/externalViewer/#)
 -> All Apps -> Search of the Transaction <br>
 There select the Version of the Fiori <br>
 <img width="350" alt="image" src="https://github.com/user-attachments/assets/36840fb1-3a9f-4bcd-81ba-21a12af5f254"> <br>
 And then Go to <i>Implementation Information</i> -> <i>Configuration</i> <br>
 <img width="350" alt="image" src="https://github.com/user-attachments/assets/62eb69cf-1dac-4777-8ce2-7eca840f98d7"> <br>
 >[!NOTE]
 > Here you see all the relevant informations about the APP <br>
 > Technical Catalog, Business Catalog, Business Group, OData, SAPUI5 , Tile Title , Semantic Object , Target Mapping etc. 

 If you see a Role in the Configuration then you can assign the Role into the user and the user can see the App in Fiori Lanchpad <br>
 but if you dont see the Role then you have to create one. <br>

 Now lets see how you can do that. <br>

 First , create a [Business Catalog](#Create-Business-Catalog-Tile) (If you dont have one ) Without a Tile or Target Mapping , those you will be take them from Technical Catalog <br>

 Then take the Technical Catalog from the Fiori Library and Search it in the `/N/UI2/FLPD_CUST` Launch SAP FIORI Launchpad designer <br>
 In the Tile section <br>
 <img width="350" alt="image" src="https://github.com/user-attachments/assets/03c94e30-a93f-4bba-98a2-179888140e72"> <br>
 Look for the App you are intrested in and drag it so the <i>Create Reference</i> icon appears <br>
 <img width="350" alt="image" src="https://github.com/user-attachments/assets/9d814e16-c9b1-4bfb-a948-ec54227607dd"> <br>
 When you will drag there , you will be asked to Select a Catalog then choose the Business Catalog you created above. <br>
 Do the Same with Target Mapping <br>
 <img width="350" alt="image" src="https://github.com/user-attachments/assets/9971c29d-791e-4015-b813-2ca2829ebbb6"> <br>
 Reference Option is in Buttom Rigth Corner <br>
 <img width="350" alt="image" src="https://github.com/user-attachments/assets/011035a9-8005-4b91-a807-434e19cfbe0b"> <br>

 Then Put it or Create a [Business Group](#Create-Business-Group) and a [Role](#Create-Role) <br>
 

 > [!IMPORTANT]
 > When you create something with Reference you cant change it or Translate it. <br>
 > Basically, when something is Referenced if SAP makes a change in the App the app will be updated, <br>
 > If you want to Change and Translate the App you need to break the Reference 
 
 
 # Authorization Issues 
 When the user have Authorization Errors you need to go in Transaction `SU53` <br>
 and Select the Icon ![image](https://github.com/user-attachments/assets/4302c73a-7c8d-4b45-b081-f82f6c8b560d) <br>
 to see the authorization errors from a diffrent user.

 Here you need to see the Column <i>Application Name</i> to match the App which the error occurs <br>
 Then take the <i>Authorization Object</i> and its <i>Values</i> and put it in the role of the app with the errors. <br>

 In the Role, go to Authorizations Tab with Change and press the <i>Manually</i> Button ![image](https://github.com/user-attachments/assets/213e159e-6bad-4855-907a-3dca41ef1f69) <br>
 Enter the Authorization Object , maintain the Values from SU53 and Generate the Profile.

 # Copy Standard Role to Z*
 It is importan to Copy Standard Roles in order to add extra Authorization Objects.
 You can Copy Standard Role to Z but to be activated properly you need to do some extra steps. <br>
 If you dont then the user whould see any tiles.<br>
 
 First , go to [Fiori Libraty](https://fioriappslibrary.hana.ondemand.com/sap/fix/externalViewer/#)
 -> All Apps -> Search of the Transaction <br>
 Search for the App you want
 There select the Version of the Fiori <br>
 <img width="350" alt="image" src="https://github.com/user-attachments/assets/36840fb1-3a9f-4bcd-81ba-21a12af5f254"> <br>
 And then Go to <i>Implementation Information</i> -> <i>Configuration</i> <br>
 <img width="350" alt="image" src="https://github.com/user-attachments/assets/62eb69cf-1dac-4777-8ce2-7eca840f98d7"> <br>
 The Role is always in the Bottom. <br>

 Then, go to `PFCG` enter the role and press the <i>Copy</i> Button ![image](https://github.com/user-attachments/assets/4eb63a75-5cbb-4dd7-9226-4c5b81373ce3)
 and provide below the name of the Z* Role and <i>Copy All</i> ![image](https://github.com/user-attachments/assets/cddb8453-5c17-4c5e-ad13-f69a12aff841) .

 >[!NOTE]
 > To put the Role into Transport Request you need to press the <i>Transport</i> ![image](https://github.com/user-attachments/assets/5515af5d-2fd0-4c17-8e02-45394048521f)

 After that, go to Transactional Code `STC01` and enter the <i>SAP_FIORI_FCM_CONTENT_ACTIVATION</i> in the task list and press Execute <br>
 ![image](https://github.com/user-attachments/assets/bd05359a-6d9b-428d-b35d-b88b9ab5a88a) <br>

 Inside press the Button Below <br>
 Selected![image](https://github.com/user-attachments/assets/b817d259-677b-4552-85f7-a48f81b8b57f) <br>

 Filter the Z Role and Select it <br>
 Select ![image](https://github.com/user-attachments/assets/3dc8e84e-1a24-4556-899d-62e470543b88) <br>
 
 Save and go Back <br>

 You Should be Seen something like this <br>
 1 Selected ![image](https://github.com/user-attachments/assets/89cca2e5-62fd-41f1-99b2-50f60864704b) <br>

 And Press <i>Execute</i>

 In the End you should see Success Message <br>
 Success Message ![image](https://github.com/user-attachments/assets/86cee224-dd67-42a2-a60b-e43f4fe886a0)

 And then you need to go in `PFCG` Activate the Authorization Data and the Role is Ready!

 # Fiori T-Codes

 | Tcode	| Description |
 |--------|-------------|
 | /UI2/FLP               |	Launch SAP FIORI Launchpad|
 | /UI2/FLPD_CUST	        | Launch SAP FIORI Launchpad designer for customization ( client- specific )|
 | /UI2/FLPD_CONF	        | Launch SAP FIORI Launchpad designer for configuration ( cross-client ) |
 | /UI2/CUST	            | SAP FIORI Implementation Guide |
 | /UI2/FLC	              | Fiori Launchpad checks |
 | /UI2/FLIA	            | Fiori Launchpad Intent analysis |
 | /UI2/FLT	              | Fiori Launchpad Texts |
 | /UI2/FLPCM_CUST	      | SAP Fiori Launchpad Content Manager for customization |
 | /UI2/FLPCM_CONF	      | SAP Fiori Launchpad Content Manager for configuration |
 | /UI2/SEMOBJ_SAP	      | Gives list of all Semantic objects delivered by SAP |
 | /UI2/SEMOBJ	          | To define custom Semantic objects |
 | /n/IWFND/MAINT_SERVICE	| Activate and maintain Odata services| 
 | /n/IWFND/ERROR_LOG	    | SAP Gateway error log | 
 | /n/UI2/GW_SYS_ALIAS	  | SAP Gateway: Manage SAP system alias |
 | /n/IWFND/CACHE_CLEANUP | Clear BackEnd |
 | /n/IWBEP/CACHE_CLEANUP | Clear FrontEnd|
 | /n/IWFND/V4_ADMIN      |  For Odata Group|
