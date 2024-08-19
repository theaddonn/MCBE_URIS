## Protocol URIs
These URLs can be used to launch the game or perform specific actions.
Some of these actions cannot be done in-game so these URLs are used to perform them.
These links were gathered by reverse engineering the latest Windows client binary (1.21.2 at the time) and by using already documented URIs.

#### Shared protocols
- `ms-xbl-multiplayer://`
	Appears to be a common Xbox Live multiplayer invite protocol.
#### Minecraft
- `minecraft://`
#### Minecraft Preview
- `minecraft-preview://`

## Available URIs
#### `/`
If nothing is specified, it just launches the game.
##### Parameters
- `Editor`
    Launches the game into Editor mode.
    - Accepts: **Boolean**
- `addExternalServer`
    Saves an external server to the server list. Does not connect to that server, though.
    - Example: `Cubecraft|mco.cubecraft.net:19132`
- `load`
    Appears to be the same as the world id, the one stored inside the `minecraftWorlds` folder.
    You can use this to launch straight into a world from outside the app.
    - Accepts: **String**
- `edu`
    Can be either `1` or `0`. Seemingly not relevant for release client.
    - Accepts: **Number**
- `openMarketplaceInventory`
    Opens the current user's Marketplace Inventory.
    - Accepts:
        - `Owned`
        - `RealmsPlusCurrent`
        - `RealmsPlusRemoved`
        - `Subscriptions`
- `openCsbPDPScreen`
	Opens the Marketplace Pass screen.
	- Accepts:
		- `Home`
		- `Subscribe`
		- `Content`
		- `Faq`
- `getLayoutPage`
	 Can be used to show to navigate to different parts of the store.
	 `Search_SearchHome` navigates to the search screen.
	 `MultiItemPage_CoinScreen` navigates to the Minecoins screen.
	 `MultiItemPageStoreRoot` navigates to the Marketplace's homepage.
	 `CreatorPage_master_player_account!` followed by a creator's ID.
	 `ItemDetail_` followed by a product's UUID.
	 `BundleDetail_` followed by a bundle's UUID.
- `inviteID`
    Used for accepting Xbox live invites.
- `showHowToPlayScreen`
    Can be either `1` or `0`. Opens the how-to-play screen.
- `showStoreHomeScreen`
    Can be either `1` or `0`. Opens the Marketplace.
- `showOfferCollection`
- `showMineCoinOffers`
    Can be either `1` or `0`. Opens the Minecoin purchase screen.
- `showHowToPlayScreen`
    Can be either `1` or `0`. Opens the how-to-play screen.
- `oculus_launched`
    Can be either `1` or `0`. A shortcut to the game for Oculus (VR) users.
- `slashcommand`
    Executes a command in the current server. This will disconnect the user if used in a local world.
    - Accept: **String**
- `import`
    Imports content, could possibly be any type.
    - Accept: **String**
- `importload`
- `importtemplate`
  Imports a world template.
    - Accept: **String**
- `importaddon`
  Imports an addon.
    - Accept: **String**
- `importpack`
  Imports a resource or behavior pack.
    - Accept: **String**
- `originalpath`
- `fromtempfile`
    Seems to be unused
#### `/acceptRealmInvite`
Accepts a realm invite
##### Parameters
- `inviteID`
    The realm invite code.
    - Example: `ecldDbao75U`
#### `/connect`
Can be used for connecting to a server or opening a local world.
##### Parameters
- `localLevelId`
    Appears to be the same as the world id inside the `minecraftWorlds` folder.
- `serverUrl`
    The IP of the server.
- `serverPort`
    The port of the server that you're trying to connect to. Required if `serverUrl` is specified.
#### `/localLevelId`
Appears to be the same as the world id, the one stored inside the `minecraftWorlds` folder.
You can use this to launch straight into a world from outside the app. 
### `/localWorld`
You can use this to launch straight into a world from outside the app with the world's name.
#### `/connectToRealm`
##### Parameters
- `realmId`
	Connects to a realm.
- `inviteID`
  Accepts a realm invite and starts connecting.
- `autoConnect`
	If the client should connect or not after accepting the realm invite specified using `inviteID`.
	- Accepts: **Boolean**
#### `/mode`
##### Parameters
- `NoPause`
    Disables the game from pausing as normal when the window is not focused. Also works if the game is already open.
    - Accepts: **Boolean**
- `OpenXR`
    Opens the game in VR mode.
    - Accepts: **Boolean**
- `Oculus`
- `WindowsMR`
- `ProcessKey`
#### `/openStore`
Opens the Marketplace if no parameters are present.
##### Parameters
- `showStoreOffer`
    The UUID of a product. Opens the store entry for an item.
    - Accepts: **UUID (v4)**
    - Example: [`68b4c786-53b4-4d73-b95c-b060d7cc99c6`](https://minecraft.net/en-us/marketplace/pdp?id=68b4c786-53b4-4d73-b95c-b060d7cc99c6)
#### `/?showOfferCollection`
Not succrently known what this does.
##### Parameters
- unknown
#### `/openServersTab`
Opens the servers list.
#### `/showDressingRoomOffer`
Opens the dressing room and shows that single persona item. You can get these from [minecraftpal.com](https://minecraftpal.com).
##### Parameters
- `offerID`
    The UUID of the persona item.
    - Accepts: **UUID (v4)**
#### `/showProfileScreen`
Opens the dressing room.
#### `/joinGathering`
##### Parameters
- `gatheringId`
    The id of an active gathering.
    - Accepts: **UUID (v4)**


### Sources & Credit
- Most of the Information was provided by [@DarkGamerYT](https://github.com/DarkGamerYT)
- A lot of other information via reverse engineering is from [phasephasephase/MCBEProtocolURIs](https://github.com/phasephasephase/MCBEProtocolURIs)
- I also did some reverse engineering and added my findings

