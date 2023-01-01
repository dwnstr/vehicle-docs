# ULC for Server Owners

## ULC for Server Owners

### How to Setup ULC in your Server

#### Installation

1. Extract `ulc` from your download.
2. Place `ulc` anywhere in your resources folder.
3. Add `ensure ulc` to your server.cfg

#### Configuration

The only necessary configuration step is to add or configure vehicles. There are two possible methods.

1. Automatically import vehicle configurations from vehicle resources.
2. Manually add vehicle configurations to the `Config.Vehicles` table.

**How to Import an Included Config File**

Some vehicle resources may come with a `ulc.lua` file.

If this is the case all you have to do to configure the vehicle is add the resource name to the `Config.ExternalVehResources` table.

Example:

```lua
ExternalVehResources = {
  "my-vehicle-resource",
},
```

**How to Manually Configure a Vehicle**

If the vehicle did not come with a `ulc.lua` file, you will need to manually create a configuration for the vehicle. You can either add this configuration directly to the `config.lua` in the `Config.Vehicles` table, or you can create a `ulc.lua` file in the vehicle resource and follow the same instructions as above.

For details on all configurations, see the config value documentation below.
