# esx-metaitemclothes!

[adasdasd](https://user-images.githubusercontent.com/68826839/120798051-787ff880-c545-11eb-9b54-6cba1a74de0c.png)


qb-inventory/server/main.lua
Bu eventi bulup bunla değiştirin

RegisterServerEvent("inventory:server:UseItemSlot")
AddEventHandler('inventory:server:UseItemSlot', function(slot)
	local src = source
	local Player = ESX.GetPlayerFromId(src)
	local itemData = Player.GetItemBySlot(slot)
	if itemData ~= nil then
		local itemInfo =  ESX.GetItems()[tostring(itemData.name)]
		if itemData.type == "weapon" then
			if itemData.info.quality ~= nil then
				if itemData.info.quality >= 0 then
					TriggerClientEvent("inventory:client:UseWeapon", src, itemData, true)
				else
					TriggerClientEvent("inventory:client:UseWeapon", src, itemData, false)
				end
			else
				TriggerClientEvent("inventory:client:UseWeapon", src, itemData, true)
			end
			TriggerClientEvent('inventory:client:ItemBox', src, itemInfo, "use")
		elseif itemData.usable  then
			TriggerClientEvent("inventory:client:useitemkkkkk",src,itemData)
			TriggerClientEvent('inventory:client:ItemBox', src, itemInfo, "use")
			if itemData.name == "pantolon" then
				TriggerClientEvent('inventory:client:ItemBox',src,ESX.GetItems()["pantolon"],'remove',1)
				xPlayer.Functions.RemoveItem('pantolon', 1, itemData.slot)
				TriggerClientEvent("p1", src, itemData)
			elseif itemData.name == "tişört" then
				TriggerClientEvent('inventory:client:ItemBox',src,ESX.GetItems()["tişört"],'remove',1)
				xPlayer.Functions.RemoveItem('tişört', 1, itemData.slot)
				TriggerClientEvent("t1", src, itemData)
			elseif itemData.name == "kask" then
				TriggerClientEvent('inventory:client:ItemBox',src,ESX.GetItems()["kask"],'remove',1)
				xPlayer.Functions.RemoveItem('kask', 1, itemData.slot)
				TriggerClientEvent("h1", src, itemData)
			elseif itemData.name == "ayakkabı" then
				TriggerClientEvent('inventory:client:ItemBox',src,ESX.GetItems()["ayakkabı"],'remove',1)
				xPlayer.Functions.RemoveItem('ayakkabı', 1, itemData.slot)
				TriggerClientEvent("s1", src, itemData)
			elseif itemData.name == "maske" then
				TriggerClientEvent('inventory:client:ItemBox',src,ESX.GetItems()["maske"],'remove',1)
				xPlayer.Functions.RemoveItem('maske', 1, itemData.slot)
				TriggerClientEvent("m1", src, itemData)
			elseif itemData.name == "saat" then
				TriggerClientEvent('inventory:client:ItemBox',src,ESX.GetItems()["saat"],'remove',1)
				xPlayer.Functions.RemoveItem('saat', 1, itemData.slot)
				TriggerClientEvent("w1", src, itemData)
			elseif itemData.name == "çanta" then
				TriggerClientEvent('inventory:client:ItemBox',src,ESX.GetItems()["çanta"],'remove',1)
				xPlayer.Functions.RemoveItem('çanta', 1, itemData.slot)
				TriggerClientEvent("b1", src, itemData)
			elseif itemData.name == "gözlük" then
				TriggerClientEvent('inventory:client:ItemBox',src,ESX.GetItems()["gözlük"],'remove',1)
				xPlayer.Functions.RemoveItem('gözlük', 1, itemData.slot)
				TriggerClientEvent("g1", src, itemData)
			elseif itemData.name == "kolye" then
				TriggerClientEvent('inventory:client:ItemBox',src,ESX.GetItems()["kolye"],'remove',1)
				xPlayer.Functions.RemoveItem('kolye', 1, itemData.slot)
				TriggerClientEvent("n1", src, itemData)
			elseif itemData.name == "zırh" then
				TriggerClientEvent('inventory:client:ItemBox',src,ESX.GetItems()["zırh"],'remove',1)
				xPlayer.Functions.RemoveItem('zırh', 1, itemData.slot)
				TriggerClientEvent("v1", src, itemData)
			elseif itemData.name == "ceket" then
				TriggerClientEvent('inventory:client:ItemBox',src,ESX.GetItems()["ceket"],'remove',1)
				xPlayer.Functions.RemoveItem('ceket', 1, itemData.slot)
				TriggerClientEvent("j1", src, itemData)
			end
		end
	end
end)
