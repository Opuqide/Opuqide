## Opuqide

Hello! My name is Tyler, or Opuqide, and I am a Roblox **scripter**, **UI designer**, and **self-proclaimed artist :3**!!

I am the owner of [Project Alpine: Remastered](https://github.com/Project-Alpine-Remastered), a Roblox project dedicated to bringing the iPhone in Roblox. It's been my dream for around **four years** to bring an iPhone with extraordinary detail.

### Essential Information
- Age: 15
- Birthday: April 9
- Gender: Female
- Country: United States

### Programming
I like to code in C and Lua(u). Both are my favorite languages.

Example #1 - Snippet from CrystalChat, a proprietary and closed source custom chat
```luau
local function CCSProcessMessage(PlayerSource: Player, Message: string)
	if #Message > 200 then
		Message:sub(1, 200)
	end
	
	-- we'll run through a yielding test to see if the filter still works
	Debugger.ProfileBegin('CCSProcessMessageYield')
	local Success, Response = Debugger.SafeFunctionCall(function()
		Message = TextService:FilterStringAsync(Message, PlayerSource.UserId):GetNonChatStringForBroadcastAsync()
	end)
	Debugger.ProfileEnd('CCSProcessMessageYield')
	
	if Debugger.GetAllProfiles().CCSProcessMessageYield.Duration > 2 then
		CrystalChatClient:FireAllClients("SystemWarning", "The Roblox Chat Filter is currently experiencing issues and messages may be slow to appear.")
		return nil
	end
	
	if not Message then
		Debugger.DebugPrint("Error", "CrystalChatServer:CCSProcessMessage failed: %s", Response)
		return nil
	end
	
	return Message
end
```

Example #2 - Snippet from iBoot in Roblox (Project Alpine)
```luau
IBOOT_BOOT.mount_bootfs_from_device = function(device:string)
	local err = 0
	local i = 1
	local bootfs = ""

	-- see if the subdevice exists
	if not BLOCKDEV.lookup_blockdev(device) then
		DEBUG.dprintf(DEBUG.DEBUG_CRITICAL, "boot device '%s' does not exist", device)
		PLATFORM.platform_record_breadcrumb("mount_bootfs", "!lookup-blockdev")
		return -1
	end

	-- iterate over filesystems looking for one that will mount this partition

	for i = 1, 10, 1 do
		bootfs = FS.fs_get_fsname(i)
		if bootfs == nil or not bootfs then
			DEBUG.dprintf(DEBUG.DEBUG_CRITICAL, "can't find a filesystem willing to mount the boot partition")
			PLATFORM.platform_record_breadcrumb("mount_bootfs", "unknown-fs")
			return -1
		end

		DEBUG.dprintf(DEBUG.DEBUG_INFO, "trying System mount from device '%s', fs '%s', at /boot", device, bootfs)
		err = FS.fs_mount(device, bootfs, "/boot")
		if err == 0 then
			break
		else
			PLATFORM.platform_record_breadcrumb_int("fs_mount_err", err)
		end
	end

	DEBUG.dprintf(DEBUG.DEBUG_INFO, "mount successful")

	return 0
end
```

## Games
I like to play on PlayStation 5 and PC, but mostly PS5.


## Links
Discord Server: https://discord.gg/444nMqksmu
YouTube Channel: https://youtube.com/Opuqide

See you until then!! :white_heart:

XOXO, Opuqide
