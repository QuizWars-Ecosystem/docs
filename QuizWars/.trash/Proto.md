# Protocol Documentation
<a name="top"></a>

## Table of Contents

- [external/users/v1/admin.proto](#external_users_v1_admin-proto)
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
  
    - [UsersAdminService](#usersservice-v1-UsersAdminService)
  
- [external/users/v1/auth.proto](#external_users_v1_auth-proto)
    - [LinkOAuthProviderRequest](#usersservice-v1-LinkOAuthProviderRequest)
    - [LoginRequest](#usersservice-v1-LoginRequest)
    - [LoginResponse](#usersservice-v1-LoginResponse)
    - [LogoutRequest](#usersservice-v1-LogoutRequest)
    - [LogoutResponse](#usersservice-v1-LogoutResponse)
    - [OAuthLoginRequest](#usersservice-v1-OAuthLoginRequest)
    - [OAuthLoginResponse](#usersservice-v1-OAuthLoginResponse)
    - [RegisterRequest](#usersservice-v1-RegisterRequest)
    - [RegisterResponse](#usersservice-v1-RegisterResponse)
  
    - [UsersAuthService](#usersservice-v1-UsersAuthService)
  
- [external/users/v1/profile.proto](#external_users_v1_profile-proto)
    - [ChangePasswordRequest](#usersservice-v1-ChangePasswordRequest)
    - [DeleteAccountRequest](#usersservice-v1-DeleteAccountRequest)
    - [GetProfileRequest](#usersservice-v1-GetProfileRequest)
    - [GetProfileResponse](#usersservice-v1-GetProfileResponse)
    - [UpdateAvatarRequest](#usersservice-v1-UpdateAvatarRequest)
    - [UpdateProfileRequest](#usersservice-v1-UpdateProfileRequest)
  
    - [UsersProfileService](#usersservice-v1-UsersProfileService)
  
- [external/users/v1/shared.proto](#external_users_v1_shared-proto)
    - [Friend](#usersservice-v1-Friend)
    - [FriendsList](#usersservice-v1-FriendsList)
    - [Profile](#usersservice-v1-Profile)
    - [User](#usersservice-v1-User)
    - [UserAdmin](#usersservice-v1-UserAdmin)
  
    - [Status](#usersservice-v1-Status)
  
- [external/users/v1/social.proto](#external_users_v1_social-proto)
    - [AcceptFriendRequest](#usersservice-v1-AcceptFriendRequest)
    - [AddFriendRequest](#usersservice-v1-AddFriendRequest)
    - [BlockFriendRequest](#usersservice-v1-BlockFriendRequest)
    - [ListFriendsRequest](#usersservice-v1-ListFriendsRequest)
    - [RejectFriendRequest](#usersservice-v1-RejectFriendRequest)
    - [RemoveFriendRequest](#usersservice-v1-RemoveFriendRequest)
    - [UnblockFriendRequest](#usersservice-v1-UnblockFriendRequest)
  
    - [UsersSocialService](#usersservice-v1-UsersSocialService)
  
- [external/questions/v1/admin.proto](#external_questions_v1_admin-proto)
    - [CategoryFilter](#questionsservice-v1-CategoryFilter)
    - [CreateCategoryRequest](#questionsservice-v1-CreateCategoryRequest)
    - [CreateCategoryResponse](#questionsservice-v1-CreateCategoryResponse)
    - [CreateQuestionRequest](#questionsservice-v1-CreateQuestionRequest)
    - [CreatedAtFilter](#questionsservice-v1-CreatedAtFilter)
    - [DeleteQuestionOptionRequest](#questionsservice-v1-DeleteQuestionOptionRequest)
    - [DeleteQuestionRequest](#questionsservice-v1-DeleteQuestionRequest)
    - [DifficultyFilter](#questionsservice-v1-DifficultyFilter)
    - [GetFilteredQuestionsRequest](#questionsservice-v1-GetFilteredQuestionsRequest)
    - [GetFilteredQuestionsResponse](#questionsservice-v1-GetFilteredQuestionsResponse)
    - [LanguageFilter](#questionsservice-v1-LanguageFilter)
    - [TypeFilter](#questionsservice-v1-TypeFilter)
    - [UpdateCategoryRequest](#questionsservice-v1-UpdateCategoryRequest)
    - [UpdateQuestionOptionRequest](#questionsservice-v1-UpdateQuestionOptionRequest)
    - [UpdateQuestionRequest](#questionsservice-v1-UpdateQuestionRequest)
  
    - [Order](#questionsservice-v1-Order)
    - [Sort](#questionsservice-v1-Sort)
  
    - [QuestionsAdminService](#questionsservice-v1-QuestionsAdminService)
  
- [external/questions/v1/client.proto](#external_questions_v1_client-proto)
    - [GetCategoriesResponse](#questionsservice-v1-GetCategoriesResponse)
  
    - [QuestionsClientService](#questionsservice-v1-QuestionsClientService)
  
- [external/questions/v1/questions.proto](#external_questions_v1_questions-proto)
    - [GetQuestionBatchRequest](#questionsservice-v1-GetQuestionBatchRequest)
    - [GetQuestionsRequest](#questionsservice-v1-GetQuestionsRequest)
    - [QuestionsResponse](#questionsservice-v1-QuestionsResponse)
  
    - [QuestionsService](#questionsservice-v1-QuestionsService)
  
- [external/questions/v1/shared.proto](#external_questions_v1_shared-proto)
    - [Category](#questionsservice-v1-Category)
    - [Option](#questionsservice-v1-Option)
    - [Question](#questionsservice-v1-Question)
  
    - [Difficulty](#questionsservice-v1-Difficulty)
    - [Source](#questionsservice-v1-Source)
    - [Type](#questionsservice-v1-Type)
  
- [Scalar Value Types](#scalar-value-types)



<a name="external_users_v1_admin-proto"></a>
<p align="right"><a href="#top">Top</a></p>

## external/users/v1/admin.proto



<a name="usersservice-v1-BanUserRequest"></a>

### BanUserRequest



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



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| page | [uint64](#uint64) |  |  |
| size | [uint64](#uint64) |  |  |
| order | [Order](#usersservice-v1-Order) | optional |  |
| sort | [Sort](#usersservice-v1-Sort) | optional |  |
| user_rating | [RatingFiler](#usersservice-v1-RatingFiler) |  |  |
| user_coins | [CoinsFiler](#usersservice-v1-CoinsFiler) |  |  |
| user_created_at | [CreateAtFiler](#usersservice-v1-CreateAtFiler) |  |  |
| user_deleted_at | [DeletedAtFiler](#usersservice-v1-DeletedAtFiler) |  |  |






<a name="usersservice-v1-SearchUsersResponse"></a>

### SearchUsersResponse



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| users | [UserAdmin](#usersservice-v1-UserAdmin) | repeated |  |
| page | [uint64](#uint64) |  |  |
| size | [uint64](#uint64) |  |  |
| order | [Order](#usersservice-v1-Order) |  |  |
| sort | [Sort](#usersservice-v1-Sort) |  |  |
| amount | [int64](#int64) |  |  |






<a name="usersservice-v1-UnbanUserRequest"></a>

### UnbanUserRequest



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| user_id | [string](#string) |  |  |






<a name="usersservice-v1-UpdateUserRoleRequest"></a>

### UpdateUserRoleRequest



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| user_id | [string](#string) |  |  |
| role | [Role](#usersservice-v1-Role) |  |  |





 


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


 

 


<a name="usersservice-v1-UsersAdminService"></a>

### UsersAdminService


| Method Name | Request Type | Response Type | Description |
| ----------- | ------------ | ------------- | ------------|
| SearchUsers | [SearchUsersRequest](#usersservice-v1-SearchUsersRequest) | [SearchUsersResponse](#usersservice-v1-SearchUsersResponse) |  |
| GetUserByIdentifier | [GetUserByIdentifierRequest](#usersservice-v1-GetUserByIdentifierRequest) | [UserAdmin](#usersservice-v1-UserAdmin) |  |
| UpdateUserRole | [UpdateUserRoleRequest](#usersservice-v1-UpdateUserRoleRequest) | [.google.protobuf.Empty](#google-protobuf-Empty) |  |
| BanUser | [BanUserRequest](#usersservice-v1-BanUserRequest) | [.google.protobuf.Empty](#google-protobuf-Empty) |  |
| UnbanUser | [UnbanUserRequest](#usersservice-v1-UnbanUserRequest) | [.google.protobuf.Empty](#google-protobuf-Empty) |  |

 



<a name="external_users_v1_auth-proto"></a>
<p align="right"><a href="#top">Top</a></p>

## external/users/v1/auth.proto



<a name="usersservice-v1-LinkOAuthProviderRequest"></a>

### LinkOAuthProviderRequest



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| user_id | [string](#string) |  |  |
| provider | [string](#string) |  |  |
| code | [string](#string) |  |  |






<a name="usersservice-v1-LoginRequest"></a>

### LoginRequest



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| username | [string](#string) |  |  |
| email | [string](#string) |  |  |
| password | [string](#string) |  |  |






<a name="usersservice-v1-LoginResponse"></a>

### LoginResponse



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| token | [string](#string) |  |  |
| profile | [Profile](#usersservice-v1-Profile) |  |  |






<a name="usersservice-v1-LogoutRequest"></a>

### LogoutRequest



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| user_id | [string](#string) |  |  |






<a name="usersservice-v1-LogoutResponse"></a>

### LogoutResponse







<a name="usersservice-v1-OAuthLoginRequest"></a>

### OAuthLoginRequest



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| token | [string](#string) |  |  |
| provider | [string](#string) |  |  |
| code | [string](#string) |  |  |






<a name="usersservice-v1-OAuthLoginResponse"></a>

### OAuthLoginResponse



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| profile | [Profile](#usersservice-v1-Profile) |  |  |
| is_new_user | [bool](#bool) |  |  |






<a name="usersservice-v1-RegisterRequest"></a>

### RegisterRequest



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| avatar_id | [int32](#int32) |  | Avatar ID INT32 |
| username | [string](#string) |  |  |
| email | [string](#string) |  |  |
| password | [string](#string) |  |  |






<a name="usersservice-v1-RegisterResponse"></a>

### RegisterResponse



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| token | [string](#string) |  |  |
| profile | [Profile](#usersservice-v1-Profile) |  |  |





 

 

 


<a name="usersservice-v1-UsersAuthService"></a>

### UsersAuthService


| Method Name | Request Type | Response Type | Description |
| ----------- | ------------ | ------------- | ------------|
| Register | [RegisterRequest](#usersservice-v1-RegisterRequest) | [RegisterResponse](#usersservice-v1-RegisterResponse) | Some custom commentary |
| Login | [LoginRequest](#usersservice-v1-LoginRequest) | [LoginResponse](#usersservice-v1-LoginResponse) |  |
| Logout | [LogoutRequest](#usersservice-v1-LogoutRequest) | [.google.protobuf.Empty](#google-protobuf-Empty) |  |
| OAuthLogin | [OAuthLoginRequest](#usersservice-v1-OAuthLoginRequest) | [OAuthLoginResponse](#usersservice-v1-OAuthLoginResponse) |  |
| LinkOAuthProvider | [LinkOAuthProviderRequest](#usersservice-v1-LinkOAuthProviderRequest) | [.google.protobuf.Empty](#google-protobuf-Empty) |  |

 



<a name="external_users_v1_profile-proto"></a>
<p align="right"><a href="#top">Top</a></p>

## external/users/v1/profile.proto



<a name="usersservice-v1-ChangePasswordRequest"></a>

### ChangePasswordRequest



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| user_id | [string](#string) |  |  |
| password | [string](#string) |  |  |






<a name="usersservice-v1-DeleteAccountRequest"></a>

### DeleteAccountRequest



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| user_id | [string](#string) |  |  |






<a name="usersservice-v1-GetProfileRequest"></a>

### GetProfileRequest



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| user_id | [string](#string) |  |  |
| username | [string](#string) |  |  |






<a name="usersservice-v1-GetProfileResponse"></a>

### GetProfileResponse



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| profile | [Profile](#usersservice-v1-Profile) |  |  |
| user | [User](#usersservice-v1-User) |  |  |






<a name="usersservice-v1-UpdateAvatarRequest"></a>

### UpdateAvatarRequest



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| user_id | [string](#string) |  |  |
| avatar_id | [int32](#int32) |  |  |






<a name="usersservice-v1-UpdateProfileRequest"></a>

### UpdateProfileRequest



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| user_id | [string](#string) |  |  |
| username | [string](#string) | optional |  |





 

 

 


<a name="usersservice-v1-UsersProfileService"></a>

### UsersProfileService


| Method Name | Request Type | Response Type | Description |
| ----------- | ------------ | ------------- | ------------|
| GetProfile | [GetProfileRequest](#usersservice-v1-GetProfileRequest) | [GetProfileResponse](#usersservice-v1-GetProfileResponse) |  |
| UpdateProfile | [UpdateProfileRequest](#usersservice-v1-UpdateProfileRequest) | [.google.protobuf.Empty](#google-protobuf-Empty) |  |
| UpdateAvatar | [UpdateAvatarRequest](#usersservice-v1-UpdateAvatarRequest) | [.google.protobuf.Empty](#google-protobuf-Empty) |  |
| ChangePassword | [ChangePasswordRequest](#usersservice-v1-ChangePasswordRequest) | [.google.protobuf.Empty](#google-protobuf-Empty) |  |
| DeleteAccount | [DeleteAccountRequest](#usersservice-v1-DeleteAccountRequest) | [.google.protobuf.Empty](#google-protobuf-Empty) |  |

 



<a name="external_users_v1_shared-proto"></a>
<p align="right"><a href="#top">Top</a></p>

## external/users/v1/shared.proto



<a name="usersservice-v1-Friend"></a>

### Friend



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| user | [User](#usersservice-v1-User) |  |  |
| status | [Status](#usersservice-v1-Status) |  |  |






<a name="usersservice-v1-FriendsList"></a>

### FriendsList



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| friends | [Friend](#usersservice-v1-Friend) | repeated |  |






<a name="usersservice-v1-Profile"></a>

### Profile



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| id | [string](#string) |  |  |
| avatar_id | [int32](#int32) |  |  |
| username | [string](#string) |  |  |
| email | [string](#string) |  |  |
| rating | [int32](#int32) |  |  |
| coins | [int64](#int64) |  |  |
| created_at | [google.protobuf.Timestamp](#google-protobuf-Timestamp) |  |  |
| last_login_at | [google.protobuf.Timestamp](#google-protobuf-Timestamp) | optional |  |






<a name="usersservice-v1-User"></a>

### User



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| id | [string](#string) |  |  |
| avatar_id | [int32](#int32) |  |  |
| username | [string](#string) |  |  |
| rating | [int32](#int32) |  |  |
| created_at | [google.protobuf.Timestamp](#google-protobuf-Timestamp) |  |  |
| last_login_at | [google.protobuf.Timestamp](#google-protobuf-Timestamp) | optional |  |






<a name="usersservice-v1-UserAdmin"></a>

### UserAdmin



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| id | [string](#string) |  |  |
| avatar_id | [int32](#int32) |  |  |
| username | [string](#string) |  |  |
| email | [string](#string) |  |  |
| rating | [int32](#int32) |  |  |
| coins | [int64](#int64) |  |  |
| created_at | [google.protobuf.Timestamp](#google-protobuf-Timestamp) |  |  |
| last_login_at | [google.protobuf.Timestamp](#google-protobuf-Timestamp) | optional |  |
| deleted_at | [google.protobuf.Timestamp](#google-protobuf-Timestamp) | optional |  |





 


<a name="usersservice-v1-Status"></a>

### Status


| Name | Number | Description |
| ---- | ------ | ----------- |
| STATUS_UNSPECIFIED | 0 |  |
| STATUS_PENDING | 1 |  |
| STATUS_ACCEPTED | 2 |  |
| STATUS_BLOCKED | 3 |  |


 

 

 



<a name="external_users_v1_social-proto"></a>
<p align="right"><a href="#top">Top</a></p>

## external/users/v1/social.proto



<a name="usersservice-v1-AcceptFriendRequest"></a>

### AcceptFriendRequest



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| recipient_id | [string](#string) |  |  |
| requester_id | [string](#string) |  |  |






<a name="usersservice-v1-AddFriendRequest"></a>

### AddFriendRequest



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| requester_id | [string](#string) |  |  |
| recipient_id | [string](#string) |  |  |






<a name="usersservice-v1-BlockFriendRequest"></a>

### BlockFriendRequest



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| user_id | [string](#string) |  |  |
| friend_id | [string](#string) |  |  |






<a name="usersservice-v1-ListFriendsRequest"></a>

### ListFriendsRequest



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| user_id | [string](#string) |  |  |






<a name="usersservice-v1-RejectFriendRequest"></a>

### RejectFriendRequest



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| recipient_id | [string](#string) |  |  |
| requester_id | [string](#string) |  |  |






<a name="usersservice-v1-RemoveFriendRequest"></a>

### RemoveFriendRequest



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| requester_id | [string](#string) |  |  |
| friend_id | [string](#string) |  |  |






<a name="usersservice-v1-UnblockFriendRequest"></a>

### UnblockFriendRequest



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| user_id | [string](#string) |  |  |
| friend_id | [string](#string) |  |  |





 

 

 


<a name="usersservice-v1-UsersSocialService"></a>

### UsersSocialService


| Method Name | Request Type | Response Type | Description |
| ----------- | ------------ | ------------- | ------------|
| AddFriend | [AddFriendRequest](#usersservice-v1-AddFriendRequest) | [.google.protobuf.Empty](#google-protobuf-Empty) |  |
| AcceptFriend | [AcceptFriendRequest](#usersservice-v1-AcceptFriendRequest) | [.google.protobuf.Empty](#google-protobuf-Empty) |  |
| RejectFriend | [RejectFriendRequest](#usersservice-v1-RejectFriendRequest) | [.google.protobuf.Empty](#google-protobuf-Empty) |  |
| RemoveFriend | [RemoveFriendRequest](#usersservice-v1-RemoveFriendRequest) | [.google.protobuf.Empty](#google-protobuf-Empty) |  |
| ListFriends | [ListFriendsRequest](#usersservice-v1-ListFriendsRequest) | [FriendsList](#usersservice-v1-FriendsList) |  |
| BlockFriend | [BlockFriendRequest](#usersservice-v1-BlockFriendRequest) | [.google.protobuf.Empty](#google-protobuf-Empty) |  |
| UnblockFriend | [UnblockFriendRequest](#usersservice-v1-UnblockFriendRequest) | [.google.protobuf.Empty](#google-protobuf-Empty) |  |

 



<a name="external_questions_v1_admin-proto"></a>
<p align="right"><a href="#top">Top</a></p>

## external/questions/v1/admin.proto



<a name="questionsservice-v1-CategoryFilter"></a>

### CategoryFilter



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| categories | [int32](#int32) | repeated |  |






<a name="questionsservice-v1-CreateCategoryRequest"></a>

### CreateCategoryRequest



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| name | [string](#string) |  |  |






<a name="questionsservice-v1-CreateCategoryResponse"></a>

### CreateCategoryResponse



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| id | [int32](#int32) |  |  |






<a name="questionsservice-v1-CreateQuestionRequest"></a>

### CreateQuestionRequest



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| type | [Type](#questionsservice-v1-Type) |  |  |
| difficulty | [Difficulty](#questionsservice-v1-Difficulty) |  |  |
| category_id | [int32](#int32) |  |  |
| text | [string](#string) |  |  |
| options | [Option](#questionsservice-v1-Option) | repeated |  |
| language | [string](#string) |  |  |
| media_url | [string](#string) | optional |  |






<a name="questionsservice-v1-CreatedAtFilter"></a>

### CreatedAtFilter



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| from | [google.protobuf.Timestamp](#google-protobuf-Timestamp) |  |  |
| to | [google.protobuf.Timestamp](#google-protobuf-Timestamp) |  |  |






<a name="questionsservice-v1-DeleteQuestionOptionRequest"></a>

### DeleteQuestionOptionRequest



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| id | [string](#string) |  |  |






<a name="questionsservice-v1-DeleteQuestionRequest"></a>

### DeleteQuestionRequest



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| id | [string](#string) |  |  |






<a name="questionsservice-v1-DifficultyFilter"></a>

### DifficultyFilter



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| difficulties | [Difficulty](#questionsservice-v1-Difficulty) | repeated |  |






<a name="questionsservice-v1-GetFilteredQuestionsRequest"></a>

### GetFilteredQuestionsRequest



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| page | [uint64](#uint64) |  |  |
| size | [uint64](#uint64) |  |  |
| order | [Order](#questionsservice-v1-Order) | optional |  |
| sort | [Sort](#questionsservice-v1-Sort) | optional |  |
| type_filter | [TypeFilter](#questionsservice-v1-TypeFilter) | optional |  |
| difficulty_filter | [DifficultyFilter](#questionsservice-v1-DifficultyFilter) | optional |  |
| category_filter | [CategoryFilter](#questionsservice-v1-CategoryFilter) | optional |  |
| language_filter | [LanguageFilter](#questionsservice-v1-LanguageFilter) | optional |  |
| create_at_filter | [CreatedAtFilter](#questionsservice-v1-CreatedAtFilter) | optional |  |






<a name="questionsservice-v1-GetFilteredQuestionsResponse"></a>

### GetFilteredQuestionsResponse



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| questions | [Question](#questionsservice-v1-Question) | repeated |  |
| page | [uint64](#uint64) |  |  |
| size | [uint64](#uint64) |  |  |
| order | [Order](#questionsservice-v1-Order) |  |  |
| sort | [Sort](#questionsservice-v1-Sort) |  |  |
| amount | [int64](#int64) |  |  |






<a name="questionsservice-v1-LanguageFilter"></a>

### LanguageFilter



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| languages | [string](#string) | repeated |  |






<a name="questionsservice-v1-TypeFilter"></a>

### TypeFilter



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| types | [Type](#questionsservice-v1-Type) | repeated |  |






<a name="questionsservice-v1-UpdateCategoryRequest"></a>

### UpdateCategoryRequest



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| id | [int32](#int32) |  |  |
| name | [string](#string) |  |  |






<a name="questionsservice-v1-UpdateQuestionOptionRequest"></a>

### UpdateQuestionOptionRequest



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| id | [string](#string) |  |  |
| text | [string](#string) | optional |  |
| is_correct | [bool](#bool) | optional |  |






<a name="questionsservice-v1-UpdateQuestionRequest"></a>

### UpdateQuestionRequest



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| id | [string](#string) |  |  |
| type | [Type](#questionsservice-v1-Type) | optional |  |
| difficulty | [Difficulty](#questionsservice-v1-Difficulty) | optional |  |
| category_id | [int32](#int32) | optional |  |
| text | [string](#string) | optional |  |
| language | [string](#string) | optional |  |





 


<a name="questionsservice-v1-Order"></a>

### Order


| Name | Number | Description |
| ---- | ------ | ----------- |
| ORDER_UNSPECIFIED | 0 |  |
| ORDER_ID | 1 |  |
| ORDER_TEXT | 2 |  |
| ORDER_TYPE | 3 |  |
| ORDER_DIFFICULTY | 4 |  |
| ORDER_CATEGORY | 5 |  |
| ORDER_LANGUAGE | 6 |  |
| ORDER_CREATED_AT | 7 |  |



<a name="questionsservice-v1-Sort"></a>

### Sort


| Name | Number | Description |
| ---- | ------ | ----------- |
| SORT_UNSPECIFIED | 0 |  |
| SORT_ASC | 1 |  |
| SORT_DESC | 2 |  |


 

 


<a name="questionsservice-v1-QuestionsAdminService"></a>

### QuestionsAdminService


| Method Name | Request Type | Response Type | Description |
| ----------- | ------------ | ------------- | ------------|
| GetFilteredQuestions | [GetFilteredQuestionsRequest](#questionsservice-v1-GetFilteredQuestionsRequest) | [GetFilteredQuestionsResponse](#questionsservice-v1-GetFilteredQuestionsResponse) |  |
| CreateCategory | [CreateCategoryRequest](#questionsservice-v1-CreateCategoryRequest) | [CreateCategoryResponse](#questionsservice-v1-CreateCategoryResponse) |  |
| CreateQuestion | [CreateQuestionRequest](#questionsservice-v1-CreateQuestionRequest) | [.google.protobuf.Empty](#google-protobuf-Empty) |  |
| UpdateCategory | [UpdateCategoryRequest](#questionsservice-v1-UpdateCategoryRequest) | [.google.protobuf.Empty](#google-protobuf-Empty) |  |
| UpdateQuestion | [UpdateQuestionRequest](#questionsservice-v1-UpdateQuestionRequest) | [.google.protobuf.Empty](#google-protobuf-Empty) |  |
| UpdateQuestionOption | [UpdateQuestionOptionRequest](#questionsservice-v1-UpdateQuestionOptionRequest) | [.google.protobuf.Empty](#google-protobuf-Empty) |  |
| DeleteQuestion | [DeleteQuestionRequest](#questionsservice-v1-DeleteQuestionRequest) | [.google.protobuf.Empty](#google-protobuf-Empty) |  |
| DeleteQuestionOption | [DeleteQuestionOptionRequest](#questionsservice-v1-DeleteQuestionOptionRequest) | [.google.protobuf.Empty](#google-protobuf-Empty) |  |

 



<a name="external_questions_v1_client-proto"></a>
<p align="right"><a href="#top">Top</a></p>

## external/questions/v1/client.proto



<a name="questionsservice-v1-GetCategoriesResponse"></a>

### GetCategoriesResponse



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| categories | [Category](#questionsservice-v1-Category) | repeated |  |





 

 

 


<a name="questionsservice-v1-QuestionsClientService"></a>

### QuestionsClientService


| Method Name | Request Type | Response Type | Description |
| ----------- | ------------ | ------------- | ------------|
| GetCategories | [.google.protobuf.Empty](#google-protobuf-Empty) | [GetCategoriesResponse](#questionsservice-v1-GetCategoriesResponse) |  |

 



<a name="external_questions_v1_questions-proto"></a>
<p align="right"><a href="#top">Top</a></p>

## external/questions/v1/questions.proto



<a name="questionsservice-v1-GetQuestionBatchRequest"></a>

### GetQuestionBatchRequest



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| types | [Type](#questionsservice-v1-Type) | repeated |  |
| sources | [Source](#questionsservice-v1-Source) | repeated |  |
| difficulties | [Difficulty](#questionsservice-v1-Difficulty) | repeated |  |
| categories_ids | [int32](#int32) | repeated |  |
| language | [string](#string) |  |  |
| amount | [int32](#int32) |  |  |






<a name="questionsservice-v1-GetQuestionsRequest"></a>

### GetQuestionsRequest



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| difficulty | [Difficulty](#questionsservice-v1-Difficulty) |  |  |
| language | [string](#string) |  |  |
| category_id | [int32](#int32) |  |  |
| amount | [int32](#int32) |  |  |






<a name="questionsservice-v1-QuestionsResponse"></a>

### QuestionsResponse



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| questions | [Question](#questionsservice-v1-Question) | repeated |  |





 

 

 


<a name="questionsservice-v1-QuestionsService"></a>

### QuestionsService


| Method Name | Request Type | Response Type | Description |
| ----------- | ------------ | ------------- | ------------|
| GetQuestions | [GetQuestionsRequest](#questionsservice-v1-GetQuestionsRequest) | [QuestionsResponse](#questionsservice-v1-QuestionsResponse) |  |
| GetQuestionBatch | [GetQuestionBatchRequest](#questionsservice-v1-GetQuestionBatchRequest) | [QuestionsResponse](#questionsservice-v1-QuestionsResponse) |  |

 



<a name="external_questions_v1_shared-proto"></a>
<p align="right"><a href="#top">Top</a></p>

## external/questions/v1/shared.proto



<a name="questionsservice-v1-Category"></a>

### Category



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| id | [int32](#int32) |  |  |
| name | [string](#string) |  |  |






<a name="questionsservice-v1-Option"></a>

### Option



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| id | [string](#string) |  |  |
| text | [string](#string) |  |  |
| is_correct | [bool](#bool) |  |  |






<a name="questionsservice-v1-Question"></a>

### Question



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| id | [string](#string) |  |  |
| type | [Type](#questionsservice-v1-Type) |  |  |
| source | [Source](#questionsservice-v1-Source) |  |  |
| difficulty | [Difficulty](#questionsservice-v1-Difficulty) |  |  |
| category | [Category](#questionsservice-v1-Category) |  |  |
| text | [string](#string) |  |  |
| options | [Option](#questionsservice-v1-Option) | repeated |  |
| language | [string](#string) |  |  |
| created_at | [google.protobuf.Timestamp](#google-protobuf-Timestamp) |  |  |





 


<a name="questionsservice-v1-Difficulty"></a>

### Difficulty


| Name | Number | Description |
| ---- | ------ | ----------- |
| DIFFICULTY_UNSPECIFIED | 0 |  |
| DIFFICULTY_EASY | 1 |  |
| DIFFICULTY_MEDIUM | 2 |  |
| DIFFICULTY_HARD | 3 |  |
| DIFFICULTY_VERY_HARD | 4 |  |



<a name="questionsservice-v1-Source"></a>

### Source


| Name | Number | Description |
| ---- | ------ | ----------- |
| SOURCE_UNSPECIFIED | 0 |  |
| SOURCE_TEXT | 1 |  |
| SOURCE_IMAGE | 2 |  |
| SOURCE_AUDIO | 3 |  |
| SOURCE_ANIMATION | 4 |  |
| SOURCE_VIDEO | 5 |  |



<a name="questionsservice-v1-Type"></a>

### Type


| Name | Number | Description |
| ---- | ------ | ----------- |
| TYPE_UNSPECIFIED | 0 |  |
| TYPE_SINGLE | 1 |  |
| TYPE_MULTI | 2 |  |
| TYPE_BETTING | 3 |  |


 

 

 



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

