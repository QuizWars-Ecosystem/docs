# Table of Contents


external/users/v1/admin.proto

- Services
    - [UsersAdminService]
  


- Messages
    - [BanUserRequest]
    - [CoinsFiler]
    - [CreateAtFiler]
    - [DeletedAtFiler]
    - [GetUserByIdentifierRequest]
    - [RatingFiler]
    - [SearchUsersRequest]
    - [SearchUsersResponse]
    - [UnbanUserRequest]
    - [UpdateUserRoleRequest]
  


- Enums
    - [Order]
    - [Role]
    - [Sort]
  


external/users/v1/auth.proto

- Services
    - [UsersAuthService]
  


- Messages
    - [LinkOAuthProviderRequest]
    - [LoginRequest]
    - [LoginResponse]
    - [LogoutRequest]
    - [OAuthLoginRequest]
    - [OAuthLoginResponse]
    - [RegisterRequest]
    - [RegisterResponse]
  



external/users/v1/profile.proto

- Services
    - [UsersProfileService]
  


- Messages
    - [ChangePasswordRequest]
    - [DeleteAccountRequest]
    - [GetProfileRequest]
    - [GetProfileResponse]
    - [UpdateAvatarRequest]
    - [UpdateProfileRequest]
  



external/users/v1/shared.proto


- Messages
    - [Friend]
    - [FriendsList]
    - [Profile]
    - [User]
    - [UserAdmin]
  


- Enums
    - [Status]
  


external/users/v1/social.proto

- Services
    - [UsersSocialService]
  


- Messages
    - [AcceptFriendRequest]
    - [AddFriendRequest]
    - [BlockFriendRequest]
    - [ListFriendsRequest]
    - [RejectFriendRequest]
    - [RemoveFriendRequest]
    - [UnblockFriendRequest]
  



- [Scalar Value Types](#scalar-value-types)



# UsersAdminService {#usersservicev1usersadminservice}
Users Admin Service has methods for manage user's profiles via Admin access

## SearchUsers

> **rpc** SearchUsers([SearchUsersRequest]
    [SearchUsersResponse]

Search users profile with pagination and filters
Auth: Admin
## GetUserByIdentifier

> **rpc** GetUserByIdentifier([GetUserByIdentifierRequest]
    [UserAdmin]

Get User profile with Admin view, possible use one of profile identifier.
It can be id, email or username.
Auth: Admin
## UpdateUserRole

> **rpc** UpdateUserRole([UpdateUserRoleRequest]
    [.google.protobuf.Empty]

Set new user profile role
Auth: Super
## BanUser

> **rpc** BanUser([BanUserRequest]
    [.google.protobuf.Empty]

Method for ban user, it's happens by set delete_at a date. After ban, impossible login.
Auth: Super
## UnbanUser

> **rpc** UnbanUser([UnbanUserRequest]
    [.google.protobuf.Empty]

Method for unban user profile, it's happens by set delete_at a null.
Auth: Super
 <!-- end methods -->
 <!-- end services -->

# Messages


## BanUserRequest {#banuserrequest}
Represent argument of method for ban user, user id required


| Field | Type | Description |
| ----- | ---- | ----------- |
| user_id | [ string](#string) | none |
 <!-- end Fields -->
 <!-- end HasFields -->


## CoinsFiler {#coinsfiler}



| Field | Type | Description |
| ----- | ---- | ----------- |
| from | [ int64](#int64) | none |
| to | [ int64](#int64) | none |
 <!-- end Fields -->
 <!-- end HasFields -->


## CreateAtFiler {#createatfiler}



| Field | Type | Description |
| ----- | ---- | ----------- |
| from | [ google.protobuf.Timestamp](#googleprotobuftimestamp) | none |
| to | [ google.protobuf.Timestamp](#googleprotobuftimestamp) | none |
 <!-- end Fields -->
 <!-- end HasFields -->


## DeletedAtFiler {#deletedatfiler}



| Field | Type | Description |
| ----- | ---- | ----------- |
| from | [ google.protobuf.Timestamp](#googleprotobuftimestamp) | none |
| to | [ google.protobuf.Timestamp](#googleprotobuftimestamp) | none |
 <!-- end Fields -->
 <!-- end HasFields -->


## GetUserByIdentifierRequest {#getuserbyidentifierrequest}
Represent of request argument what allow admin get specified user by one of his identifier: id, username, email


| Field | Type | Description |
| ----- | ---- | ----------- |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) identifier.user_id | [ string](#string) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) identifier.username | [ string](#string) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) identifier.email | [ string](#string) | none |
 <!-- end Fields -->
 <!-- end HasFields -->


## RatingFiler {#ratingfiler}



| Field | Type | Description |
| ----- | ---- | ----------- |
| from | [ int32](#int32) | none |
| to | [ int32](#int32) | none |
 <!-- end Fields -->
 <!-- end HasFields -->


## SearchUsersRequest {#searchusersrequest}
Represent filter for searching users profiles, has required fields


| Field | Type | Description |
| ----- | ---- | ----------- |
| page | [ uint64](#uint64) | Value of taget page, default must be 1 |
| size | [ uint64](#uint64) | Amount of desired entities amount, try use with limit |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) _order.order | [optional Order](#order) | Optional order, default is username |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) _sort.sort | [optional Sort](#sort) | Optional sort, default is ASC |
| user_rating | [ RatingFiler](#ratingfiler) | Optional filter, from-to rating window |
| user_coins | [ CoinsFiler](#coinsfiler) | Optional filter, from-to coins window |
| user_created_at | [ CreateAtFiler](#createatfiler) | Optional filter, from-to register date window |
| user_deleted_at | [ DeletedAtFiler](#deletedatfiler) | Optional filter, from-to deleted (banned) date window |
 <!-- end Fields -->
 <!-- end HasFields -->


## SearchUsersResponse {#searchusersresponse}
Represent result of searching users.


| Field | Type | Description |
| ----- | ---- | ----------- |
| users | [repeated UserAdmin](#useradmin) | Array of user's profiles that has additional fields that able only for admin view |
| page | [ uint64](#uint64) | Current page, allow work with pagination |
| size | [ uint64](#uint64) | Current page size value |
| order | [ Order](#order) | Order what was used to get current result |
| sort | [ Sort](#sort) | Sort type that was used for get current result |
| amount | [ int64](#int64) | Amount of all user's profiles that able to get using the same request filter |
 <!-- end Fields -->
 <!-- end HasFields -->


## UnbanUserRequest {#unbanuserrequest}
Represent argument of method for unban user, user id required


| Field | Type | Description |
| ----- | ---- | ----------- |
| user_id | [ string](#string) | none |
 <!-- end Fields -->
 <!-- end HasFields -->


## UpdateUserRoleRequest {#updateuserrolerequest}
Represent argument of request for set a user new role, user id and enum role required


| Field | Type | Description |
| ----- | ---- | ----------- |
| user_id | [ string](#string) | none |
| role | [ Role](#role) | none |
 <!-- end Fields -->
 <!-- end HasFields -->
 <!-- end messages -->

# Enums


## Order {#order}


| Name | Number | Description |
| ---- | ------ | ----------- |
| ORDER_UNSPECIFIED | 0 | none |
| ORDER_ID | 1 | none |
| ORDER_USERNAME | 2 | none |
| ORDER_EMAIL | 3 | none |
| ORDER_RATING | 4 | none |
| ORDER_COINS | 5 | none |
| ORDER_CREATED_AT | 6 | none |
| ORDER_DELETED_AT | 7 | none |




## Role {#role}


| Name | Number | Description |
| ---- | ------ | ----------- |
| ROLE_UNSPECIFIED | 0 | none |
| ROLE_USER | 1 | none |
| ROLE_ADMIN | 2 | none |
| ROLE_SUPER | 3 | none |




## Sort {#sort}


| Name | Number | Description |
| ---- | ------ | ----------- |
| SORT_UNSPECIFIED | 0 | none |
| SORT_ASC | 1 | none |
| SORT_DESC | 2 | none |


 <!-- end Enums -->


# UsersAuthService {#usersservicev1usersauthservice}
User Auth Service manage of user's register, logging and logout in system

## Register

> **rpc** Register([RegisterRequest]
    [RegisterResponse]

Method for register new user in system, all filed are required. Returns created user profile on success and JWT token for usage
## Login

> **rpc** Login([LoginRequest]
    [LoginResponse]

Allow already registered users login in system using email or username an password. Returns user profile and JWT token
## Logout

> **rpc** Logout([LogoutRequest]
    [.google.protobuf.Empty]

Logout method mark user profile inactive in system and update git last login date. Can be use by user or client
## OAuthLogin

> **rpc** OAuthLogin([OAuthLoginRequest]
    [OAuthLoginResponse]

UNIMPLEMENTED - Allow register of login users using OAuth2 tools. Returns user profile, JWT token and bool flag if user is new
## LinkOAuthProvider

> **rpc** LinkOAuthProvider([LinkOAuthProviderRequest]
    [.google.protobuf.Empty]

UNIMPLEMENTED - Allow already registered user connect system profile with his account that provides OAuth2 tools
 <!-- end methods -->
 <!-- end services -->

# Messages


## LinkOAuthProviderRequest {#linkoauthproviderrequest}
Represents rpc method argument for link existing system account with OAuth2 providers


| Field | Type | Description |
| ----- | ---- | ----------- |
| user_id | [ string](#string) | none |
| provider | [ string](#string) | none |
| code | [ string](#string) | none |
 <!-- end Fields -->
 <!-- end HasFields -->


## LoginRequest {#loginrequest}
Represents login method argument that allows user login in system


| Field | Type | Description |
| ----- | ---- | ----------- |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) identifier.username | [ string](#string) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) identifier.email | [ string](#string) | none |
| password | [ string](#string) | none |
 <!-- end Fields -->
 <!-- end HasFields -->


## LoginResponse {#loginresponse}
Represents result of login request, contain user's profile and JWT token


| Field | Type | Description |
| ----- | ---- | ----------- |
| token | [ string](#string) | none |
| profile | [ Profile](#profile) | none |
 <!-- end Fields -->
 <!-- end HasFields -->


## LogoutRequest {#logoutrequest}
Message for request to logout, user id is required


| Field | Type | Description |
| ----- | ---- | ----------- |
| user_id | [ string](#string) | none |
 <!-- end Fields -->
 <!-- end HasFields -->


## OAuthLoginRequest {#oauthloginrequest}
Message is argument of request to register or login in system using OAuth2 providers


| Field | Type | Description |
| ----- | ---- | ----------- |
| token | [ string](#string) | Provider token |
| provider | [ string](#string) | Name of provider |
| code | [ string](#string) | Code of provider |
 <!-- end Fields -->
 <!-- end HasFields -->


## OAuthLoginResponse {#oauthloginresponse}
Represents a result of method for login or register via OAuth2


| Field | Type | Description |
| ----- | ---- | ----------- |
| profile | [ Profile](#profile) | none |
| is_new_user | [ bool](#bool) | none |
 <!-- end Fields -->
 <!-- end HasFields -->


## RegisterRequest {#registerrequest}
Represents register method argument for register new profile in system. All fields are required for action


| Field | Type | Description |
| ----- | ---- | ----------- |
| avatar_id | [ int32](#int32) | none |
| username | [ string](#string) | none |
| email | [ string](#string) | none |
| password | [ string](#string) | none |
 <!-- end Fields -->
 <!-- end HasFields -->


## RegisterResponse {#registerresponse}
Message that contain registered profile and JWT token for future usage


| Field | Type | Description |
| ----- | ---- | ----------- |
| token | [ string](#string) | none |
| profile | [ Profile](#profile) | none |
 <!-- end Fields -->
 <!-- end HasFields -->
 <!-- end messages -->

# Enums
 <!-- end Enums -->


# UsersProfileService {#usersservicev1usersprofileservice}
User Profile Service contain methods for self manage user profile

## GetProfile

> **rpc** GetProfile([GetProfileRequest]
    [GetProfileResponse]

Method allow get existing user profile user his id or username. For self profile request user get more infirmation, for side user less
Auth: Self/User
## UpdateProfile

> **rpc** UpdateProfile([UpdateProfileRequest]
    [.google.protobuf.Empty]

Method allow user update his account
Auth: Self
## UpdateAvatar

> **rpc** UpdateAvatar([UpdateAvatarRequest]
    [.google.protobuf.Empty]

Method allow user update hiw profile avatar
Auth: Self
## ChangePassword

> **rpc** ChangePassword([ChangePasswordRequest]
    [.google.protobuf.Empty]

Method allow user reset his password
Auth: Self
## DeleteAccount

> **rpc** DeleteAccount([DeleteAccountRequest]
    [.google.protobuf.Empty]

Method allow user delete his account (not fully)
Auth: Self
 <!-- end methods -->
 <!-- end services -->

# Messages


## ChangePasswordRequest {#changepasswordrequest}
Represents request message for reset user's profile password. User id always required


| Field | Type | Description |
| ----- | ---- | ----------- |
| user_id | [ string](#string) | none |
| password | [ string](#string) | none |
 <!-- end Fields -->
 <!-- end HasFields -->


## DeleteAccountRequest {#deleteaccountrequest}
Message that required user id for mark his account as deleted in system


| Field | Type | Description |
| ----- | ---- | ----------- |
| user_id | [ string](#string) | none |
 <!-- end Fields -->
 <!-- end HasFields -->


## GetProfileRequest {#getprofilerequest}
Represents request argument for getting user profile. Required on of identifier


| Field | Type | Description |
| ----- | ---- | ----------- |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) identifier.user_id | [ string](#string) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) identifier.username | [ string](#string) | none |
 <!-- end Fields -->
 <!-- end HasFields -->


## GetProfileResponse {#getprofileresponse}
Represents request result of getting user profile. Contain one of possible data. Profile what can be requester only his owner
or User (short profile) what can be requested anyone


| Field | Type | Description |
| ----- | ---- | ----------- |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) data.profile | [ Profile](#profile) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) data.user | [ User](#user) | none |
 <!-- end Fields -->
 <!-- end HasFields -->


## UpdateAvatarRequest {#updateavatarrequest}
Represents request argument for set new profile's avatar id. User id always required


| Field | Type | Description |
| ----- | ---- | ----------- |
| user_id | [ string](#string) | none |
| avatar_id | [ int32](#int32) | none |
 <!-- end Fields -->
 <!-- end HasFields -->


## UpdateProfileRequest {#updateprofilerequest}
Represents request argument for update some user's account data. User id always required, any others files are optional.
They can be provided seperated or in one message


| Field | Type | Description |
| ----- | ---- | ----------- |
| user_id | [ string](#string) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) _username.username | [optional string](#string) | none |
 <!-- end Fields -->
 <!-- end HasFields -->
 <!-- end messages -->

# Enums
 <!-- end Enums -->


 <!-- end services -->

# Messages


## Friend {#friend}



| Field | Type | Description |
| ----- | ---- | ----------- |
| user | [ User](#user) | A user that interact with another |
| status | [ Status](#status) | Status of friendship, this is shared status, it means if one person accepted request on fiendship, it will be accepted for both |
 <!-- end Fields -->
 <!-- end HasFields -->


## FriendsList {#friendslist}
Message represents user's friends, actually is a list of user profiles with friendship status


| Field | Type | Description |
| ----- | ---- | ----------- |
| friends | [repeated Friend](#friend) | none |
 <!-- end Fields -->
 <!-- end HasFields -->


## Profile {#profile}
Message represents user profile that can be shown only for his owner


| Field | Type | Description |
| ----- | ---- | ----------- |
| id | [ string](#string) | User id is actually UUID |
| avatar_id | [ int32](#int32) | Is a id of avatars preset |
| username | [ string](#string) | Username is a string, no longer then 32 char |
| email | [ string](#string) | Email is a string, no longer then 128 char |
| rating | [ int32](#int32) | Is a int filed that represents user rating |
| coins | [ int64](#int64) | Is a int value that represents amount of user's coins |
| created_at | [ google.protobuf.Timestamp](#googleprotobuftimestamp) | Is a date when user was registered, cannot be null |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) _last_login_at.last_login_at | [optional google.protobuf.Timestamp](#googleprotobuftimestamp) | Is a date when user was last active, can be null |
 <!-- end Fields -->
 <!-- end HasFields -->


## User {#user}
Message represents user profile that can be shown anyone


| Field | Type | Description |
| ----- | ---- | ----------- |
| id | [ string](#string) | User id is actually UUID |
| avatar_id | [ int32](#int32) | Is a id of avatars preset |
| username | [ string](#string) | Username is a string, no longer then 32 char |
| rating | [ int32](#int32) | Is a int filed that represents user rating |
| created_at | [ google.protobuf.Timestamp](#googleprotobuftimestamp) | Is a date when user was registered, cannot be null |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) _last_login_at.last_login_at | [optional google.protobuf.Timestamp](#googleprotobuftimestamp) | Is a date when user was last active, can be null |
 <!-- end Fields -->
 <!-- end HasFields -->


## UserAdmin {#useradmin}
Message represents user profile that can be shown only admin


| Field | Type | Description |
| ----- | ---- | ----------- |
| id | [ string](#string) | User id is actually UUID |
| avatar_id | [ int32](#int32) | Is a id of avatars preset |
| username | [ string](#string) | Username is a string, no longer then 32 char |
| email | [ string](#string) | Email is a string, no longer then 128 char |
| rating | [ int32](#int32) | Is a int filed that represents user rating |
| coins | [ int64](#int64) | Is a int value that represents amount of user's coins |
| created_at | [ google.protobuf.Timestamp](#googleprotobuftimestamp) | Is a date when user was registered, cannot be null |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) _last_login_at.last_login_at | [optional google.protobuf.Timestamp](#googleprotobuftimestamp) | Is a date when user was last active, can be null |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) _deleted_at.deleted_at | [optional google.protobuf.Timestamp](#googleprotobuftimestamp) | Is a date when user profile was deleted by owner or banned by admin |
 <!-- end Fields -->
 <!-- end HasFields -->
 <!-- end messages -->

# Enums


## Status {#status}


| Name | Number | Description |
| ---- | ------ | ----------- |
| STATUS_UNSPECIFIED | 0 | Is technical status |
| STATUS_PENDING | 1 | Means that requested waiting for recipient action |
| STATUS_ACCEPTED | 2 | Means that friendship is active for both users |
| STATUS_BLOCKED | 3 | Means that one of friend did block another and friendship exists but is inactive |


 <!-- end Enums -->


# UsersSocialService {#usersservicev1userssocialservice}
Users Social Service allow users be active with others users

## AddFriend

> **rpc** AddFriend([AddFriendRequest]
    [.google.protobuf.Empty]

Method for asking another user be friends. It adds requested user request message on friendship
## AcceptFriend

> **rpc** AcceptFriend([AcceptFriendRequest]
    [.google.protobuf.Empty]

Method that set message on friendship active and adds users in shared relation (make users mutual related)
## RejectFriend

> **rpc** RejectFriend([RejectFriendRequest]
    [.google.protobuf.Empty]

Method that reject message on friendship from requester
## RemoveFriend

> **rpc** RemoveFriend([RemoveFriendRequest]
    [.google.protobuf.Empty]

Method removes already created and active friendship between two users
## ListFriends

> **rpc** ListFriends([ListFriendsRequest]
    [FriendsList]

Method for get all relations for specified user, result is users list with any relation (active/inactive)
## BlockFriend

> **rpc** BlockFriend([BlockFriendRequest]
    [.google.protobuf.Empty]

Method for blocking friend (they will be not able to communicate witch each other)
Auth: Self
## UnblockFriend

> **rpc** UnblockFriend([UnblockFriendRequest]
    [.google.protobuf.Empty]

Method is reverse action of blocking. Allows user remove friend from black list
Auth: Self
 <!-- end methods -->
 <!-- end services -->

# Messages


## AcceptFriendRequest {#acceptfriendrequest}
Represents request argument for make friendship active, all fields are required


| Field | Type | Description |
| ----- | ---- | ----------- |
| recipient_id | [ string](#string) | Recipient id is id of user that got friendship request on want to act |
| requester_id | [ string](#string) | Requester id is id of user that was a initiator of the action |
 <!-- end Fields -->
 <!-- end HasFields -->


## AddFriendRequest {#addfriendrequest}
Represents request argument for creating friendship, all fields are required


| Field | Type | Description |
| ----- | ---- | ----------- |
| requester_id | [ string](#string) | Requested id is id of user that is initiator of action |
| recipient_id | [ string](#string) | Recipient id is id of user that is terminator of action |
 <!-- end Fields -->
 <!-- end HasFields -->


## BlockFriendRequest {#blockfriendrequest}
Represents request argument for block friend. It will mark their friendship as blocked


| Field | Type | Description |
| ----- | ---- | ----------- |
| user_id | [ string](#string) | none |
| friend_id | [ string](#string) | none |
 <!-- end Fields -->
 <!-- end HasFields -->


## ListFriendsRequest {#listfriendsrequest}
Represents request argument for getting all his friends as a list


| Field | Type | Description |
| ----- | ---- | ----------- |
| user_id | [ string](#string) | User id of initiator of get list friends action (self) |
 <!-- end Fields -->
 <!-- end HasFields -->


## RejectFriendRequest {#rejectfriendrequest}
Represents request argument for rejecting proposed friendship, all fields are required


| Field | Type | Description |
| ----- | ---- | ----------- |
| recipient_id | [ string](#string) | Recipient id is id of user that got request on friendship but wants to reject it |
| requester_id | [ string](#string) | Requester id is id of user that was a initiator of the action |
 <!-- end Fields -->
 <!-- end HasFields -->


## RemoveFriendRequest {#removefriendrequest}
Represents request argument for remove already existing friendship between users, all fields are required


| Field | Type | Description |
| ----- | ---- | ----------- |
| requester_id | [ string](#string) | Recipient id is id of user that is initiator of removing friendship |
| friend_id | [ string](#string) | Friend id is id of user that is a friend of removing friendship initiator |
 <!-- end Fields -->
 <!-- end HasFields -->


## UnblockFriendRequest {#unblockfriendrequest}
Represents request argument for unblock friend. It will mark their friendship as active (accepted)


| Field | Type | Description |
| ----- | ---- | ----------- |
| user_id | [ string](#string) | none |
| friend_id | [ string](#string) | none |
 <!-- end Fields -->
 <!-- end HasFields -->
 <!-- end messages -->

# Enums
 <!-- end Enums -->
 <!-- end Files -->

# Scalar Value Types

| .proto Type | Notes | Go Type | Java Type | Python Type |
| ----------- | ----- | -------- | --------- | ----------- |
| <div><h4 id="double" /></div><a name="double" /> double |  | float64 | double | float |
| <div><h4 id="float" /></div><a name="float" /> float |  | float32 | float | float |
| <div><h4 id="int32" /></div><a name="int32" /> int32 | Uses variable-length encoding. Inefficient for encoding negative numbers – if your field is likely to have negative values, use sint32 instead. | int32 | int | int |
| <div><h4 id="int64" /></div><a name="int64" /> int64 | Uses variable-length encoding. Inefficient for encoding negative numbers – if your field is likely to have negative values, use sint64 instead. | int64 | long | int/long |
| <div><h4 id="uint32" /></div><a name="uint32" /> uint32 | Uses variable-length encoding. | uint32 | int | int/long |
| <div><h4 id="uint64" /></div><a name="uint64" /> uint64 | Uses variable-length encoding. | uint64 | long | int/long |
| <div><h4 id="sint32" /></div><a name="sint32" /> sint32 | Uses variable-length encoding. Signed int value. These more efficiently encode negative numbers than regular int32s. | int32 | int | int |
| <div><h4 id="sint64" /></div><a name="sint64" /> sint64 | Uses variable-length encoding. Signed int value. These more efficiently encode negative numbers than regular int64s. | int64 | long | int/long |
| <div><h4 id="fixed32" /></div><a name="fixed32" /> fixed32 | Always four bytes. More efficient than uint32 if values are often greater than 2^28. | uint32 | int | int |
| <div><h4 id="fixed64" /></div><a name="fixed64" /> fixed64 | Always eight bytes. More efficient than uint64 if values are often greater than 2^56. | uint64 | long | int/long |
| <div><h4 id="sfixed32" /></div><a name="sfixed32" /> sfixed32 | Always four bytes. | int32 | int | int |
| <div><h4 id="sfixed64" /></div><a name="sfixed64" /> sfixed64 | Always eight bytes. | int64 | long | int/long |
| <div><h4 id="bool" /></div><a name="bool" /> bool |  | bool | boolean | boolean |
| <div><h4 id="string" /></div><a name="string" /> string | A string must always contain UTF-8 encoded or 7-bit ASCII text. | string | String | str/unicode |
| <div><h4 id="bytes" /></div><a name="bytes" /> bytes | May contain any arbitrary sequence of bytes. | []byte | ByteString | str |
