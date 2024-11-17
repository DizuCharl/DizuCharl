class HauntedMask:
    def __init__(self):
        self.controlled = False

    def possess(self, character):
        if not self.controlled:
            character.is_possessed = True
            self.controlled = True
            print(f"{character.name} is now possessed by the mask!")

    def remove_possession(self, character):
        if self.controlled:
            character.is_possessed = False
            self.controlled = False
            print(f"{character.name} has freed themselves from the mask's control!")

class Character:
    def __init__(self, name):
        self.name = name
        self.is_possessed = False

# Example usage
mask = HauntedMask()
player = Character("Alex")

mask.possess(player)
mask.remove_possession(player)
