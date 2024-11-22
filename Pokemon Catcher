import random
import time

# ASCII Pokeball
pokeball_throw = '''
⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⣀⣠⣤⣴⣶⣶⣶⣶⣶⣶⣶⣦⣤⣀⡀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀
⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⣀⣤⣶⣿⡿⠿⠛⠛⠋⠉⠉⠉⠉⠉⠙⠛⠻⠿⣿⣿⣶⣤⡀⠀⠀⠀⠀⠀⠀⠀⠀
⠀⠀⠀⠀⠀⠀⠀⢀⣴⣾⣿⠟⠋⠁⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠈⠙⠿⣿⣷⣄⡀⠀⠀⠀⠀⠀
⠀⠀⠀⠀⠀⢀⣴⣿⡿⠋⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠈⠙⢿⣿⣦⠀⠀⠀⠀⠀
⠀⠀⠀⠀⣠⣿⡿⠋⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠻⣿⣷⡄⠀⠀⠀
⠀⠀⠀⣼⣿⡟⠁⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠈⢿⣿⣆⠀⠀
⠀⠀⣼⣿⠏⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠈⢿⣿⣆⠀
⠀⢰⣿⡟⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠈⣿⣿⡄
⠀⣿⣿⠁⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠸⣿⣧
⢸⣿⡟⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⣿⣿
⢸⣿⡇⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⣿⣿
⢸⣿⣿⡀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⣠⣿⣿
⠈⣿⣿⣿⣄⡀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⢀⣀⣤⣤⣄⣀⡀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⢀⣴⣿⣿⡿
⠀⢻⣿⡿⢿⣿⣶⣄⡀⠀⠀⠀⠀⠀⠀⢀⣴⣿⣿⠿⠟⠛⠿⢿⣿⣷℄⠀⠀⠀⠀⠀⠀⠀⣀⣤⣶⣿⡿⣿⣿⡇
⠀⠈⢿⣿⡄⠉⠛⠿⣿⣷⣶⣤⣤⣀⣠⣿⡿⠋⢠⠴⠒⠒⠲⢤⡈⠻⣿⣷⣀⣠⣤⣴⣶⣿⡿⠿⠋⠁⣰⣿⡟⠀
⠀⠀⠈⢿⣿⡄⠀⠀⠀⠈⠉⠛⠻⠿⣿⣿⡇⠀⡏⠀⠀⠀⠀⠈⡇⠀⢻⣿⡿⠿⠛⠛⠉⠁⠀⠀⠀⣰⣿⡟⠀⠀
⠀⠀⠀⠈⢿⣿⣦⠀⠀⠀⠀⠀⠀⠀⢸⣿⣧⡀⠻⣄⡀⠀⣀⡴⠃⢠⣿⣿⠁⠀⠀⠀⠀⠀⠀⢀⣼⣿⠟⠀⠀⠀
⠀⠀⠀⠀⠀⠻⣿⣷⣄⡀⠀⠀⠀⠀⠀⠙⢿⣿⣦⣄⣉⣉⣁⣤⣶⣿⠿⠁⠀⠀⠀⠀⠀⢀⣴⣿⡿⠋⠀⠀⠀⠀
⠀⠀⠀⠀⠀⠀⠈⠻⣿⣿⣦⣀⠀⠀⠀⠀⠀⠉⠛⠿⠿⠿⠿⠟⠋⠁⠀⠀⠀⠀⠀⣠⣴⣿⡿⠋⠀⠀⠀⠀⠀⠀
⠀⠀⠀⠀⠀⠀⠀⠀⠀⠙⠻⢿⣿⣶⣤⣄⣀⠀⠀⠀⠀⠀⠀⠀⠀⠀⢀⣀⣠⣤⣶⣿⡿⠟⠉⠀⠀⠀⠀⠀⠀⠀⠀
⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠈⠙⠻⠿⢿⣿⣿⣷⣶⣶⣶⣿⣿⣿⡿⠿⠛⠋⠁⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀
⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠉⠉⠉⠉⠉⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀
'''

# Full list of Pokémon
pokemon_list = [
    "Bulbasaur", "Ivysaur", "Venusaur", "Charmander", "Charmeleon", "Charizard", 
    "Squirtle", "Wartortle", "Blastoise", "Pikachu", "Raichu", "Sandshrew", 
    "Sandslash", "Nidoran♀", "Nidorina", "Nidoqueen", "Nidoran♂", "Nidorino", 
    "Nidoking", "Clefairy", "Clefable", "Vulpix", "Ninetales", "Jigglypuff", 
    "Wigglytuff", "Zubat", "Golbat", "Oddish", "Gloom", "Vileplume", "Paras", 
    "Parasect", "Venonat", "Venomoth", "Diglett", "Dugtrio", "Meowth", "Persian", 
    "Psyduck", "Golduck", "Machop", "Machoke", "Machamp", "Magnemite", "Magneton", 
    "Krabby", "Kingler", "Exeggcute", "Exeggutor", "Cubone", "Marowak", "Koffing", 
    "Weezing", "Rhyhorn", "Rhydon", "Chansey", "Tangela", "Kangaskhan", "Horsea", 
    "Seadra", "Staryu", "Starmie", "Mr. Mime", "Scyther", "Electabuzz", "Magmar", 
    "Pinsir", "Tauros", "Magikarp", "Gyarados", "Lapras", "Ditto", "Eevee", 
    "Vaporeon", "Jolteon", "Flareon", "Espeon", "Umbreon", "Leafeon", "Glaceon", 
    "Sylveon", "Snorlax", "Articuno", "Zapdos", "Moltres", "Mewtwo", "Mew"
]

# Function to simulate catching a Pokémon
def throw_pokeball():
    print("Throwing Pokéball...")
    time.sleep(1)
    print(pokeball_throw)
    time.sleep(1)
    
    # Simulate the Pokéball shaking and catching process
    print("...Shake...Shake...")
    time.sleep(2)
    
    catch = random.choice([True, False])  # Randomly decide if the Pokéball catches the Pokémon
    if catch:
        pokemon = random.choice(pokemon_list)
        print(f"Congratulations! You caught a {pokemon}!")
    else:
        print("The Pokémon escaped! Try again!")

# Run the simulation
if __name__ == "__main__":
    throw_pokeball()
