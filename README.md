## OBJECTS

### getUserInfoFromUsername
``` 
# Username               : Username of ROBLOX user.
# UserID                 : UserID of ROBLOX user.
# hasVerifiedBadge       : Is ROBLOX user has Verified badge?
# displayName            : Display name of ROBLOX user.
```

### getUserInfoFromID
``` 
# UserID                 : UserID of ROBLOX user.
# Username               : Username of ROBLOX user.
# hasVerifiedBadge       : Is ROBLOX user has Verified badge?
# displayName            : Display name of ROBLOX user.
# externalAppDisplayName : Unknown, returns null everytime.
# isBanned               : Is ROBLOX user banned?
# CreatedAt              : Creation Date of ROBLOX user.
# Description            : Description of ROBLOX user.
```


## EXAMPLES

### getUserInfoFromUsername Function

```js
async function example_UserInfoFromUsername() {
    const RobloxAPI = require("custom-robloxapi") // 2. Loading Module

    let getUserInfoFromUsername = await RobloxAPI.getUserInfoFromUsername("ROBLOX") // 3. Requesting user info with ROBLOX username.

    // 4. Checking for errors below.
    if (getUserInfoFromUsername.error && getUserInfoFromUsername.message == "Invalid Username") {
        return console.log("Provided Username is invalid!")
    } else if (getUserInfoFromUsername.error) {
        return console.log("Error catched: " + getUserInfoFromUsername.message)
    }

    console.log(getUserInfoFromUsername) // 5. Logging whole info to console.
}
example_UserInfoFromUsername() // 1. Calling function first.
```

### getUserRankInGroupFromID Function
```js
async function example_UserRankInfo() {

    const RobloxAPI = require("custom-robloxapi") // 2. Loading Module

    // 3. Requesting rank info with ROBLOX UserID + ROBLOX GroupID.
    let getGroupInfoFromID = await RobloxAPI.getUserRankInGroupFromID({ UserID: "1", GroupID: "7" }) 

    // 4. Checking for errors below.
    if (getGroupInfoFromID.error && getGroupInfoFromID.message == "Invalid UserID") {
        return console.log("Provided UserID is invalid!")
    } else if (getGroupInfoFromID.error) {
        return console.log("Error catched: " + getGroupInfoFromID.message)
    } else if (!getGroupInfoFromID.Group) {
        return console.log("Provided GroupID is invalid!")
    }

    console.log(getGroupInfoFromID) // 5. Logging whole info to console.
}
example_UserRankInfo() // 1. Calling function.
```

### getUserInfoFromID Function
```js
async function example_UserInfoFromID() {

    const RobloxAPI = require("custom-robloxapi") // 2. Loading Module

    let getUserInfoFromID = await RobloxAPI.getUserInfoFromID("1") // 3. Requesting more user info with ROBLOX UserId.

    // 4. Checking for errors below.
    if (getUserInfoFromID.error && getUserInfoFromID.message == "Invalid UserID") {
        return console.log("Provided UserID is invalid!")
    } else if (getUserInfoFromID.error) {
        return console.log("Error catched: " + getUserInfoFromID.message)
    }

    console.log(getUserInfoFromID) // 5. Logging whole info to console.

}
example_UserInfoFromID() // 1. Calling function.
```

## CHANGES

### v1.2.1
```
# New endpoint for getting user rank in a group.
# Some changes for example module.
# LICENSE changes woooo
```

### v1.2.0
```
# Added new endpoint to get more user info.
# Now all error handlers now returning "error: true" status. So errors can be handled easily now.
# Some changes for example module.
```

### v1.1.9
```
# Added error handler for undefined username.
# Some changes for example module.
```