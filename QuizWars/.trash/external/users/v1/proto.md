# Protocol Documentation
<a name="top"></a>

## Table of Contents

- [external/users/v1/admin.proto](#external_users_v1_admin-proto)
    - [UsersAdminService](#usersservice-v1-UsersAdminService)
  
    - [BanUserRequest](#usersservice-v1-BanUserRequest)
    - [CoinsFiler](#usersservice-v1-CoinsFiler)
    - [CreateAtFiler](#usersservice-v1-CreateAtFiler)
    - [DeletedAtFiler](#usersservice-v1-DeletedAtFiler)
    - [GetUserByIdentifierRequest](#usersservice-v1-GetUserByIdentifierRequest)
    - [RatingFiler](#usersservice-v1-RatingFiler)
    - [SearchUsersRequest](#usersservice-v1-SearchUsersRequest)
    - [SearchUsersResponse](#usersservice-v1-SearchUsersResponse)
    - [UnbanUserRequest](#usersservice-v1-UnbanUserRequest)
    - [UpdateUserRoleRequest](#usersservice-v1-UpdateUserRoleRequest)
  
    - [Order](#usersservice-v1-Order)
    - [Role](#usersservice-v1-Role)
    - [Sort](#usersservice-v1-Sort)
  
- [external/users/v1/auth.proto](#external_users_v1_auth-proto)
    - [UsersAuthService](#usersservice-v1-UsersAuthService)
  
    - [LinkOAuthProviderRequest](#usersservice-v1-LinkOAuthProviderRequest)
    - [LoginRequest](#usersservice-v1-LoginRequest)
    - [LoginResponse](#usersservice-v1-LoginResponse)
    - [LogoutRequest](#usersservice-v1-LogoutRequest)
    - [OAuthLoginRequest](#usersservice-v1-OAuthLoginRequest)
    - [OAuthLoginResponse](#usersservice-v1-OAuthLoginResponse)
    - [RegisterRequest](#usersservice-v1-RegisterRequest)
    - [RegisterResponse](#usersservice-v1-RegisterResponse)
  
- [external/users/v1/profile.proto](#external_users_v1_profile-proto)
    - [UsersProfileService](#usersservice-v1-UsersProfileService)
  
    - [ChangePasswordRequest](#usersservice-v1-ChangePasswordRequest)
    - [DeleteAccountRequest](#usersservice-v1-DeleteAccountRequest)
    - [GetProfileRequest](#usersservice-v1-GetProfileRequest)
    - [GetProfileResponse](#usersservice-v1-GetProfileResponse)
    - [UpdateAvatarRequest](#usersservice-v1-UpdateAvatarRequest)
    - [UpdateProfileRequest](#usersservice-v1-UpdateProfileRequest)
  
- [external/users/v1/shared.proto](#external_users_v1_shared-proto)
    - [Friend](#usersservice-v1-Friend)
    - [FriendsList](#usersservice-v1-FriendsList)
    - [Profile](#usersservice-v1-Profile)
    - [User](#usersservice-v1-User)
    - [UserAdmin](#usersservice-v1-UserAdmin)
  
    - [Status](#usersservice-v1-Status)
  
- [external/users/v1/social.proto](#external_users_v1_social-proto)
    - [UsersSocialService](#usersservice-v1-UsersSocialService)
  
    - [AcceptFriendRequest](#usersservice-v1-AcceptFriendRequest)
    - [AddFriendRequest](#usersservice-v1-AddFriendRequest)
    - [BlockFriendRequest](#usersservice-v1-BlockFriendRequest)
    - [ListFriendsRequest](#usersservice-v1-ListFriendsRequest)
    - [RejectFriendRequest](#usersservice-v1-RejectFriendRequest)
    - [RemoveFriendRequest](#usersservice-v1-RemoveFriendRequest)
    - [UnblockFriendRequest](#usersservice-v1-UnblockFriendRequest)
  
- [Scalar Value Types](#scalar-value-types)



<a name="external_users_v1_admin-proto"></a>
<p align="right"><a href="#top">Top</a></p>

## external/users/v1/admin.proto



<a name="usersservice-v1-BanUserRequest"></a>

### BanUserRequest
Represent argument of method for ban user, user id required


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| user_id | [string](#string) |  |  |






<a name="usersservice-v1-CoinsFiler"></a>

### CoinsFiler



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| from | [int64](#int64) |  |  |
| to | [int64](#int64) |  |  |






<a name="usersservice-v1-CreateAtFiler"></a>

### CreateAtFiler



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| from | [google.protobuf.Timestamp](#google-protobuf-Timestamp) |  |  |
| to | [google.protobuf.Timestamp](#google-protobuf-Timestamp) |  |  |






<a name="usersservice-v1-DeletedAtFiler"></a>

### DeletedAtFiler



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| from | [google.protobuf.Timestamp](#google-protobuf-Timestamp) |  |  |
| to | [google.protobuf.Timestamp](#google-protobuf-Timestamp) |  |  |






<a name="usersservice-v1-GetUserByIdentifierRequest"></a>

### GetUserByIdentifierRequest
Represent of request argument what allow admin get specified user by one of his identifier: id, username, email


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| user_id | [string](#string) |  |  |
| username | [string](#string) |  |  |
| email | [string](#string) |  |  |






<a name="usersservice-v1-RatingFiler"></a>

### RatingFiler



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| from | [int32](#int32) |  |  |
| to | [int32](#int32) |  |  |






<a name="usersservice-v1-SearchUsersRequest"></a>

### SearchUsersRequest
Represent filter for searching users profiles, has required fields


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| page | [uint64](#uint64) |  | Value of taget page, default must be 1 |
| size | [uint64](#uint64) |  | Amount of desired entities amount, try use with limit |
| order | [Order](#usersservice-v1-Order) | optional | Optional order, default is username |
| sort | [Sort](#usersservice-v1-Sort) | optional | Optional sort, default is ASC |
| user_rating | [RatingFiler](#usersservice-v1-RatingFiler) |  | Optional filter, from-to rating window |
| user_coins | [CoinsFiler](#usersservice-v1-CoinsFiler) |  | Optional filter, from-to coins window |
| user_created_at | [CreateAtFiler](#usersservice-v1-CreateAtFiler) |  | Optional filter, from-to register date window |
| user_deleted_at | [DeletedAtFiler](#usersservice-v1-DeletedAtFiler) |  | Optional filter, from-to deleted (banned) date window |






<a name="usersservice-v1-SearchUsersResponse"></a>

### SearchUsersResponse
Represent result of searching users.


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| users | [UserAdmin](#usersservice-v1-UserAdmin) | repeated | Array of user's profiles that has additional fields that able only for admin view |
| page | [uint64](#uint64) |  | Current page, allow work with pagination |
| size | [uint64](#uint64) |  | Current page size value |
| order | [Order](#usersservice-v1-Order) |  | Order what was used to get current result |
| sort | [Sort](#usersservice-v1-Sort) |  | Sort type that was used for get current result |
| amount | [int64](#int64) |  | Amount of all user's profiles that able to get using the same request filter |






<a name="usersservice-v1-UnbanUserRequest"></a>

### UnbanUserRequest
Represent argument of method for unban user, user id required


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| user_id | [string](#string) |  |  |






<a name="usersservice-v1-UpdateUserRoleRequest"></a>

### UpdateUserRoleRequest
Represent argument of request for set a user new role, user id and enum role required


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| user_id | [string](#string) |  |  |
| role | [Role](#usersservice-v1-Role) |  |  |





 <!-- end messages -->


<a name="usersservice-v1-Order"></a>

### Order


| Name | Number | Description |
| ---- | ------ | ----------- |
| ORDER_UNSPECIFIED | 0 |  |
| ORDER_ID | 1 |  |
| ORDER_USERNAME | 2 |  |
| ORDER_EMAIL | 3 |  |
| ORDER_RATING | 4 |  |
| ORDER_COINS | 5 |  |
| ORDER_CREATED_AT | 6 |  |
| ORDER_DELETED_AT | 7 |  |



<a name="usersservice-v1-Role"></a>

### Role


| Name | Number | Description |
| ---- | ------ | ----------- |
| ROLE_UNSPECIFIED | 0 |  |
| ROLE_USER | 1 |  |
| ROLE_ADMIN | 2 |  |
| ROLE_SUPER | 3 |  |



<a name="usersservice-v1-Sort"></a>

### Sort


| Name | Number | Description |
| ---- | ------ | ----------- |
| SORT_UNSPECIFIED | 0 |  |
| SORT_ASC | 1 |  |
| SORT_DESC | 2 |  |


 <!-- end enums -->

 <!-- end HasExtensions -->


<a name="usersservice-v1-UsersAdminService"></a>

### UsersAdminService
Users Admin Service has methods for manage user's profiles via Admin access

| Method Name | Request Type | Response Type | Description |
| ----------- | ------------ | ------------- | ------------|
| SearchUsers | [SearchUsersRequest](#usersservice-v1-SearchUsersRequest) | [SearchUsersResponse](#usersservice-v1-SearchUsersResponse) | Search users profile with pagination and filters Auth: Admin |
| GetUserByIdentifier | [GetUserByIdentifierRequest](#usersservice-v1-GetUserByIdentifierRequest) | [UserAdmin](#usersservice-v1-UserAdmin) | Get User profile with Admin view, possible use one of profile identifier. It can be id, email or username. Auth: Admin |
| UpdateUserRole | [UpdateUserRoleRequest](#usersservice-v1-UpdateUserRoleRequest) | [.google.protobuf.Empty](#google-protobuf-Empty) | Set new user profile role Auth: Super |
| BanUser | [BanUserRequest](#usersservice-v1-BanUserRequest) | [.google.protobuf.Empty](#google-protobuf-Empty) | Method for ban user, it's happens by set delete_at a date. After ban, impossible login. Auth: Super |
| UnbanUser | [UnbanUserRequest](#usersservice-v1-UnbanUserRequest) | [.google.protobuf.Empty](#google-protobuf-Empty) | Method for unban user profile, it's happens by set delete_at a null. Auth: Super |

 <!-- end services -->



<a name="external_users_v1_auth-proto"></a>
<p align="right"><a href="#top">Top</a></p>

## external/users/v1/auth.proto



<a name="usersservice-v1-LinkOAuthProviderRequest"></a>

### LinkOAuthProviderRequest
Represents rpc method argument for link existing system account with OAuth2 providers


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| user_id | [string](#string) |  |  |
| provider | [string](#string) |  |  |
| code | [string](#string) |  |  |






<a name="usersservice-v1-LoginRequest"></a>

### LoginRequest
Represents login method argument that allows user login in system


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| username | [string](#string) |  |  |
| email | [string](#string) |  |  |
| password | [string](#string) |  |  |






<a name="usersservice-v1-LoginResponse"></a>

### LoginResponse
Represents result of login request, contain user's profile and JWT token


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| token | [string](#string) |  |  |
| profile | [Profile](#usersservice-v1-Profile) |  |  |






<a name="usersservice-v1-LogoutRequest"></a>

### LogoutRequest
Message for request to logout, user id is required


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| user_id | [string](#string) |  |  |






<a name="usersservice-v1-OAuthLoginRequest"></a>

### OAuthLoginRequest
Message is argument of request to register or login in system using OAuth2 providers


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| token | [string](#string) |  | Provider token |
| provider | [string](#string) |  | Name of provider |
| code | [string](#string) |  | Code of provider |






<a name="usersservice-v1-OAuthLoginResponse"></a>

### OAuthLoginResponse
Represents a result of method for login or register via OAuth2


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| profile | [Profile](#usersservice-v1-Profile) |  |  |
| is_new_user | [bool](#bool) |  |  |






<a name="usersservice-v1-RegisterRequest"></a>

### RegisterRequest
Represents register method argument for register new profile in system. All fields are required for action


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| avatar_id | [int32](#int32) |  |  |
| username | [string](#string) |  |  |
| email | [string](#string) |  |  |
| password | [string](#string) |  |  |






<a name="usersservice-v1-RegisterResponse"></a>

### RegisterResponse
Message that contain registered profile and JWT token for future usage


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| token | [string](#string) |  |  |
| profile | [Profile](#usersservice-v1-Profile) |  |  |





 <!-- end messages -->

 <!-- end enums -->

 <!-- end HasExtensions -->


<a name="usersservice-v1-UsersAuthService"></a>

### UsersAuthService
User Auth Service manage of user's register, logging and logout in system

| Method Name | Request Type | Response Type | Description |
| ----------- | ------------ | ------------- | ------------|
| Register | [RegisterRequest](#usersservice-v1-RegisterRequest) | [RegisterResponse](#usersservice-v1-RegisterResponse) | Method for register new user in system, all filed are required. Returns created user profile on success and JWT token for usage |
| Login | [LoginRequest](#usersservice-v1-LoginRequest) | [LoginResponse](#usersservice-v1-LoginResponse) | Allow already registered users login in system using email or username an password. Returns user profile and JWT token |
| Logout | [LogoutRequest](#usersservice-v1-LogoutRequest) | [.google.protobuf.Empty](#google-protobuf-Empty) | Logout method mark user profile inactive in system and update git last login date. Can be use by user or client |
| OAuthLogin | [OAuthLoginRequest](#usersservice-v1-OAuthLoginRequest) | [OAuthLoginResponse](#usersservice-v1-OAuthLoginResponse) | UNIMPLEMENTED - Allow register of login users using OAuth2 tools. Returns user profile, JWT token and bool flag if user is new |
| LinkOAuthProvider | [LinkOAuthProviderRequest](#usersservice-v1-LinkOAuthProviderRequest) | [.google.protobuf.Empty](#google-protobuf-Empty) | UNIMPLEMENTED - Allow already registered user connect system profile with his account that provides OAuth2 tools |

 <!-- end services -->



<a name="external_users_v1_profile-proto"></a>
<p align="right"><a href="#top">Top</a></p>

## external/users/v1/profile.proto



<a name="usersservice-v1-ChangePasswordRequest"></a>

### ChangePasswordRequest
Represents request message for reset user's profile password. User id always required


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| user_id | [string](#string) |  |  |
| password | [string](#string) |  |  |






<a name="usersservice-v1-DeleteAccountRequest"></a>

### DeleteAccountRequest
Message that required user id for mark his account as deleted in system


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| user_id | [string](#string) |  |  |






<a name="usersservice-v1-GetProfileRequest"></a>

### GetProfileRequest
Represents request argument for getting user profile. Required on of identifier


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| user_id | [string](#string) |  |  |
| username | [string](#string) |  |  |






<a name="usersservice-v1-GetProfileResponse"></a>

### GetProfileResponse
Represents request result of getting user profile. Contain one of possible data. Profile what can be requester only his owner
or User (short profile) what can be requested anyone


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| profile | [Profile](#usersservice-v1-Profile) |  |  |
| user | [User](#usersservice-v1-User) |  |  |






<a name="usersservice-v1-UpdateAvatarRequest"></a>

### UpdateAvatarRequest
Represents request argument for set new profile's avatar id. User id always required


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| user_id | [string](#string) |  |  |
| avatar_id | [int32](#int32) |  |  |






<a name="usersservice-v1-UpdateProfileRequest"></a>

### UpdateProfileRequest
Represents request argument for update some user's account data. User id always required, any others files are optional.
They can be provided seperated or in one message


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| user_id | [string](#string) |  |  |
| username | [string](#string) | optional |  |





 <!-- end messages -->

 <!-- end enums -->

 <!-- end HasExtensions -->


<a name="usersservice-v1-UsersProfileService"></a>

### UsersProfileService
User Profile Service contain methods for self manage user profile

| Method Name | Request Type | Response Type | Description |
| ----------- | ------------ | ------------- | ------------|
| GetProfile | [GetProfileRequest](#usersservice-v1-GetProfileRequest) | [GetProfileResponse](#usersservice-v1-GetProfileResponse) | Method allow get existing user profile user his id or username. For self profile request user get more infirmation, for side user less Auth: Self/User |
| UpdateProfile | [UpdateProfileRequest](#usersservice-v1-UpdateProfileRequest) | [.google.protobuf.Empty](#google-protobuf-Empty) | Method allow user update his account Auth: Self |
| UpdateAvatar | [UpdateAvatarRequest](#usersservice-v1-UpdateAvatarRequest) | [.google.protobuf.Empty](#google-protobuf-Empty) | Method allow user update hiw profile avatar Auth: Self |
| ChangePassword | [ChangePasswordRequest](#usersservice-v1-ChangePasswordRequest) | [.google.protobuf.Empty](#google-protobuf-Empty) | Method allow user reset his password Auth: Self |
| DeleteAccount | [DeleteAccountRequest](#usersservice-v1-DeleteAccountRequest) | [.google.protobuf.Empty](#google-protobuf-Empty) | Method allow user delete his account (not fully) Auth: Self |

 <!-- end services -->



<a name="external_users_v1_shared-proto"></a>
<p align="right"><a href="#top">Top</a></p>

## external/users/v1/shared.proto



<a name="usersservice-v1-Friend"></a>

### Friend



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| user | [User](#usersservice-v1-User) |  | A user that interact with another |
| status | [Status](#usersservice-v1-Status) |  | Status of friendship, this is shared status, it means if one person accepted request on fiendship, it will be accepted for both |






<a name="usersservice-v1-FriendsList"></a>

### FriendsList
Message represents user's friends, actually is a list of user profiles with friendship status


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| friends | [Friend](#usersservice-v1-Friend) | repeated |  |






<a name="usersservice-v1-Profile"></a>

### Profile
Message represents user profile that can be shown only for his owner


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| id | [string](#string) |  | User id is actually UUID |
| avatar_id | [int32](#int32) |  | Is a id of avatars preset |
| username | [string](#string) |  | Username is a string, no longer then 32 char |
| email | [string](#string) |  | Email is a string, no longer then 128 char |
| rating | [int32](#int32) |  | Is a int filed that represents user rating |
| coins | [int64](#int64) |  | Is a int value that represents amount of user's coins |
| created_at | [google.protobuf.Timestamp](#google-protobuf-Timestamp) |  | Is a date when user was registered, cannot be null |
| last_login_at | [google.protobuf.Timestamp](#google-protobuf-Timestamp) | optional | Is a date when user was last active, can be null |






<a name="usersservice-v1-User"></a>

### User
Message represents user profile that can be shown anyone


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| id | [string](#string) |  | User id is actually UUID |
| avatar_id | [int32](#int32) |  | Is a id of avatars preset |
| username | [string](#string) |  | Username is a string, no longer then 32 char |
| rating | [int32](#int32) |  | Is a int filed that represents user rating |
| created_at | [google.protobuf.Timestamp](#google-protobuf-Timestamp) |  | Is a date when user was registered, cannot be null |
| last_login_at | [google.protobuf.Timestamp](#google-protobuf-Timestamp) | optional | Is a date when user was last active, can be null |






<a name="usersservice-v1-UserAdmin"></a>

### UserAdmin
Message represents user profile that can be shown only admin


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| id | [string](#string) |  | User id is actually UUID |
| avatar_id | [int32](#int32) |  | Is a id of avatars preset |
| username | [string](#string) |  | Username is a string, no longer then 32 char |
| email | [string](#string) |  | Email is a string, no longer then 128 char |
| rating | [int32](#int32) |  | Is a int filed that represents user rating |
| coins | [int64](#int64) |  | Is a int value that represents amount of user's coins |
| created_at | [google.protobuf.Timestamp](#google-protobuf-Timestamp) |  | Is a date when user was registered, cannot be null |
| last_login_at | [google.protobuf.Timestamp](#google-protobuf-Timestamp) | optional | Is a date when user was last active, can be null |
| deleted_at | [google.protobuf.Timestamp](#google-protobuf-Timestamp) | optional | Is a date when user profile was deleted by owner or banned by admin |





 <!-- end messages -->


<a name="usersservice-v1-Status"></a>

### Status


| Name | Number | Description |
| ---- | ------ | ----------- |
| STATUS_UNSPECIFIED | 0 | Is technical status |
| STATUS_PENDING | 1 | Means that requested waiting for recipient action |
| STATUS_ACCEPTED | 2 | Means that friendship is active for both users |
| STATUS_BLOCKED | 3 | Means that one of friend did block another and friendship exists but is inactive |


 <!-- end enums -->

 <!-- end HasExtensions -->

 <!-- end services -->



<a name="external_users_v1_social-proto"></a>
<p align="right"><a href="#top">Top</a></p>

## external/users/v1/social.proto



<a name="usersservice-v1-AcceptFriendRequest"></a>

### AcceptFriendRequest
Represents request argument for make friendship active, all fields are required


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| recipient_id | [string](#string) |  | Recipient id is id of user that got friendship request on want to act |
| requester_id | [string](#string) |  | Requester id is id of user that was a initiator of the action |






<a name="usersservice-v1-AddFriendRequest"></a>

### AddFriendRequest
Represents request argument for creating friendship, all fields are required


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| requester_id | [string](#string) |  | Requested id is id of user that is initiator of action |
| recipient_id | [string](#string) |  | Recipient id is id of user that is terminator of action |






<a name="usersservice-v1-BlockFriendRequest"></a>

### BlockFriendRequest
Represents request argument for block friend. It will mark their friendship as blocked


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| user_id | [string](#string) |  |  |
| friend_id | [string](#string) |  |  |






<a name="usersservice-v1-ListFriendsRequest"></a>

### ListFriendsRequest
Represents request argument for getting all his friends as a list


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| user_id | [string](#string) |  | User id of initiator of get list friends action (self) |






<a name="usersservice-v1-RejectFriendRequest"></a>

### RejectFriendRequest
Represents request argument for rejecting proposed friendship, all fields are required


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| recipient_id | [string](#string) |  | Recipient id is id of user that got request on friendship but wants to reject it |
| requester_id | [string](#string) |  | Requester id is id of user that was a initiator of the action |






<a name="usersservice-v1-RemoveFriendRequest"></a>

### RemoveFriendRequest
Represents request argument for remove already existing friendship between users, all fields are required


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| requester_id | [string](#string) |  | Recipient id is id of user that is initiator of removing friendship |
| friend_id | [string](#string) |  | Friend id is id of user that is a friend of removing friendship initiator |






<a name="usersservice-v1-UnblockFriendRequest"></a>

### UnblockFriendRequest
Represents request argument for unblock friend. It will mark their friendship as active (accepted)


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| user_id | [string](#string) |  |  |
| friend_id | [string](#string) |  |  |





 <!-- end messages -->

 <!-- end enums -->

 <!-- end HasExtensions -->


<a name="usersservice-v1-UsersSocialService"></a>

### UsersSocialService
Users Social Service allow users be active with others users

| Method Name | Request Type | Response Type | Description |
| ----------- | ------------ | ------------- | ------------|
| AddFriend | [AddFriendRequest](#usersservice-v1-AddFriendRequest) | [.google.protobuf.Empty](#google-protobuf-Empty) | Method for asking another user be friends. It adds requested user request message on friendship |
| AcceptFriend | [AcceptFriendRequest](#usersservice-v1-AcceptFriendRequest) | [.google.protobuf.Empty](#google-protobuf-Empty) | Method that set message on friendship active and adds users in shared relation (make users mutual related) |
| RejectFriend | [RejectFriendRequest](#usersservice-v1-RejectFriendRequest) | [.google.protobuf.Empty](#google-protobuf-Empty) | Method that reject message on friendship from requester |
| RemoveFriend | [RemoveFriendRequest](#usersservice-v1-RemoveFriendRequest) | [.google.protobuf.Empty](#google-protobuf-Empty) | Method removes already created and active friendship between two users |
| ListFriends | [ListFriendsRequest](#usersservice-v1-ListFriendsRequest) | [FriendsList](#usersservice-v1-FriendsList) | Method for get all relations for specified user, result is users list with any relation (active/inactive) |
| BlockFriend | [BlockFriendRequest](#usersservice-v1-BlockFriendRequest) | [.google.protobuf.Empty](#google-protobuf-Empty) | Method for blocking friend (they will be not able to communicate witch each other) Auth: Self |
| UnblockFriend | [UnblockFriendRequest](#usersservice-v1-UnblockFriendRequest) | [.google.protobuf.Empty](#google-protobuf-Empty) | Method is reverse action of blocking. Allows user remove friend from black list Auth: Self |

 <!-- end services -->



## Scalar Value Types

| .proto Type | Notes | C++ | Java | Python | Go | C# | PHP | Ruby |
| ----------- | ----- | --- | ---- | ------ | -- | -- | --- | ---- |
| <a name="double" /> double |  | double | double | float | float64 | double | float | Float |
| <a name="float" /> float |  | float | float | float | float32 | float | float | Float |
| <a name="int32" /> int32 | Uses variable-length encoding. Inefficient for encoding negative numbers – if your field is likely to have negative values, use sint32 instead. | int32 | int | int | int32 | int | integer | Bignum or Fixnum (as required) |
| <a name="int64" /> int64 | Uses variable-length encoding. Inefficient for encoding negative numbers – if your field is likely to have negative values, use sint64 instead. | int64 | long | int/long | int64 | long | integer/string | Bignum |
| <a name="uint32" /> uint32 | Uses variable-length encoding. | uint32 | int | int/long | uint32 | uint | integer | Bignum or Fixnum (as required) |
| <a name="uint64" /> uint64 | Uses variable-length encoding. | uint64 | long | int/long | uint64 | ulong | integer/string | Bignum or Fixnum (as required) |
| <a name="sint32" /> sint32 | Uses variable-length encoding. Signed int value. These more efficiently encode negative numbers than regular int32s. | int32 | int | int | int32 | int | integer | Bignum or Fixnum (as required) |
| <a name="sint64" /> sint64 | Uses variable-length encoding. Signed int value. These more efficiently encode negative numbers than regular int64s. | int64 | long | int/long | int64 | long | integer/string | Bignum |
| <a name="fixed32" /> fixed32 | Always four bytes. More efficient than uint32 if values are often greater than 2^28. | uint32 | int | int | uint32 | uint | integer | Bignum or Fixnum (as required) |
| <a name="fixed64" /> fixed64 | Always eight bytes. More efficient than uint64 if values are often greater than 2^56. | uint64 | long | int/long | uint64 | ulong | integer/string | Bignum |
| <a name="sfixed32" /> sfixed32 | Always four bytes. | int32 | int | int | int32 | int | integer | Bignum or Fixnum (as required) |
| <a name="sfixed64" /> sfixed64 | Always eight bytes. | int64 | long | int/long | int64 | long | integer/string | Bignum |
| <a name="bool" /> bool |  | bool | boolean | boolean | bool | bool | boolean | TrueClass/FalseClass |
| <a name="string" /> string | A string must always contain UTF-8 encoded or 7-bit ASCII text. | string | String | str/unicode | string | string | string | String (UTF-8) |
| <a name="bytes" /> bytes | May contain any arbitrary sequence of bytes. | string | ByteString | str | []byte | ByteString | string | String (ASCII-8BIT) |
