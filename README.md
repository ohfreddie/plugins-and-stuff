source code:

package com.freddie.plugin;

import org.bukkit.Bukkit;
import org.bukkit.command.ConsoleCommandSender;
import org.bukkit.entity.Player;
import org.bukkit.event.EventHandler;
import org.bukkit.event.Listener;
import org.bukkit.event.player.PlayerEggThrowEvent;
import org.bukkit.event.player.PlayerMoveEvent;
import org.bukkit.plugin.java.JavaPlugin;

public class Main extends JavaPlugin implements Listener{
	@Override
	public void onEnable() {
		System.out.println("start");
		Bukkit.getPluginManager().registerEvents(this, this);
	}
	@Override
	public void onDisable() {
		System.out.println("stop");
	}
	
    @EventHandler
    public void onMove (PlayerMoveEvent e) {
    	
    	e.setCancelled(true);
    	
    	
    }
	@EventHandler
	public void onThrow(PlayerEggThrowEvent e) {
		Player player = e.getPlayer();
	//System.out.println("ban "+player.getName()+" lol mad cuz bad don't throw eggs nerd.");
		ConsoleCommandSender console = Bukkit.getServer().getConsoleSender();
		String command = "ban "+player.getName()+" lol mad cuz bad don't throw eggs nerd.";
		Bukkit.dispatchCommand(console, command);
	}
}



