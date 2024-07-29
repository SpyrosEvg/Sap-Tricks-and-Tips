<h1> Fiori :cherry_blossom: </h1>

- [Expose Z* Program to Fiori](#Expose-Z*-Program-to-Fiori)<br>
  - [Create Semantic Object](#Creaete-Semantic-Object)
  - [Create A Customazing Transport Request (Optional)](#Create-A-Customazing-Transport-Request)
  - [Create Tile](#Create-App-Tile)
  - [Create Business Catalog](#Create-Business-Catalog)
  - [Create Business Catalog Tile](#Create-Business-Catalog-Tile)
  - [Create Business Catalog Target Mapping](#Create-Business-Catalog-Target-Mapping)
  - [Create Business Group](#Create-Business-Group)
  - [Create Role](#Create-Role)
  - [Tile Translation](#Tile-Translation)
- [Expose Standard App to Fiori (Techical Catalog)](#Expose-Standard-App-to-Fiori)
- [Authorization Issues](#Authorization-Issues)
- [Copy Standard Role to Z*](#Copy-Standard-Role-to-Z*)
- [Fiori T-Codes](#Fiori-T-Codes)
  
# Expose Z* Program to Fiori

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
 
 >[!NOTE]
 > In order to tranport a role, in the initial screen of the transaction there a
 > <img width="600" alt="image" src="https://github.com/user-attachments/assets/8a0db830-fd01-4084-a848-e782cbc573e3"><br>
 > Also, you need a Customazing Request for the transport.
 > If you make any changes in Business Catalog you need to remove and enter it again <br>
 > and you need to generate the Authorizations again
 
 ## Tile Translation 
 :soon: Coming Soon 
 
 # Expose Standard App to Fiori (Techical Catalog)
  https://fioriappslibrary.hana.ondemand.com/ -> All Apps -> Search with T-Code or Title 
  Select The Version of your Fiori 
  Implementation Information -> Configuration

  <img width="313" alt="image" src="https://github.com/SpyrosEvg/Abap_Code/assets/39948427/5e5f2536-925f-4ec9-90dc-66408268b896">
  <img width="61" alt="image" src="https://github.com/SpyrosEvg/Abap_Code/assets/39948427/c1784d65-ffa9-4e9e-832f-9fb02000c184">
  <img width="423" alt="image" src="https://github.com/SpyrosEvg/Abap_Code/assets/39948427/0951b900-859e-4d48-9bef-04f67daa24be">
  
  <img width="192" alt="image" src="https://github.com/SpyrosEvg/Abap_Code/assets/39948427/a7f63dd5-fcc7-4aa1-a12f-93f788edf601">

 # Authorization Issues 
 :soon: Coming Soon
 # Copy Standard Role to Z*
 :soon: Coming Soon

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
