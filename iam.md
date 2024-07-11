# Identity 

Represents a user or entity having privileges to perform actions. There are 7 types of member.

- Google Account
- Service Account
- Google Group
- Google Workspace domain
- Google Identity domain
- All Authenticated users
- All Users

## Service Accounts

Associated with an application or instance rather than a user.

## Google Group

- Collection of identities
- Useful for assigning roles to multiple users
- Identities in group acquire roles assigned to group.
- Removing user from group removes role

## Google Workspace and Identity Domain

- Google Workspace user is a member of an Organizations Google Workspace domain.
- Cloud Identity is like a workspace domain but without access to the Workspace services.

## Access Control Concepts

- Resources
- Permissions
- Roles (Predefined, Custom, Primitive)
- Policies

### Policies

Collection of logical descriptions of who has what type of access.
 - IAM policies are attached to resources.
 - They are used to enforce access control whenever that resource is accessed.
 - Defined with bindings, list of members and role granted.

 ### Bindings

 Bindings are inherited from the top level down (Organizations->Folder->Project->Resources)

 ### Primitive Roles

 - Owner - All editor permissions and permissions for the following actions: Manage roles and permisions, setup billing.
 - Editor - All viewer permissions plus actions that modify state.
 - Viewer - readonly actions which don't modify the state.

 Try not to use outside of development environments.