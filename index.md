# An Introduction to Avighna Kukreja

![My Linkedin Profile Picture](https://media.licdn.com/dms/image/D5603AQG4CF6itg2EVQ/profile-displayphoto-shrink_200_200/0/1711919472591?e=1718236800&v=beta&t=kaRmno8DQ1_wNkzKfz3dFkm_ozMDc9ghrPkp1AoFzOY)

## Who I am

Hello I am Avighna Kukreja. I am a third year Computer Science student. I transfered in from Diablo Valley Community College. I make and play a variety of video games, here is my top 10.

1. Terraria
2. Super Smash Bros Melee
3. Mindustry
4. BTD5
5. Minecraft
6. AM2R
7. New Super Mario Bros Wii
8. Paper Mario TTYD
9. Dokapon Kingdom
10. Hollow Knight

I, in fact, play Melee so much with my sister and friends that I have become quite good from a casual perspective. I go to tournaments and lose to **every** player there but I don't *lose* to any of my friends. To quote one of my friends Aidan.

> "bro every time we play melee no matter what EVERY TIME I’m always mad"
> — Aidan (03/07/2024 8:38 PM)

## My programming journey
I started programming in 3rd grade on Scratch. My parents didnt buy me many video games growing up, so I thought if I could program games myself, I wouldn't need my parents to buy games. Over the years I learned Python, Java and eventually C++. I only switched languages when my games got so complex that the languages themselves were not efficient enough to run my games at a full framerate. I will paste my favorite code block I have written in C++

```
inline pair<int, int> flippedIndex(int num, vector<pair<int, int>>& degree45, int subtract = 0) {
	int actualNum = num % degree45.size();
	int falseNum = (num - actualNum) / degree45.size();
	if (falseNum % 2) { // REVERSE
		actualNum = degree45.size() - actualNum - 1;
	}
	int first = degree45[actualNum].first - subtract;
	int second = degree45[actualNum].second;
	if (((falseNum + 1) / 2) % 2) { // SWAP
		swap(first, second);
	}
	first = (((falseNum + 2) / 4) % 2) ? -first : first; // FIRST NEGATIVE
	second = ((falseNum / 4) % 2) ? -second : second; // SECOND NEGATIVE
	return {first, second};
}

inline bool inRange(int n, int s, int l) {
	return n > s && n < s + l;
}

void spiralPerPixel(Uint32* pixels, Uint32* newPixels, vector<pair<int, int>>& degree45, pair<int, int>& center, SDL_Rect& texture_rect, int z, int r, SDL_PixelFormat* format, int transitionFrames, double val) {
	pair<int, int> start = flippedIndex(z, degree45) + center;
	pair<int, int> finish = flippedIndex(z + val, degree45) + center;
	if (inRange(start.first, texture_rect.x, texture_rect.w) && inRange(start.second, texture_rect.y, texture_rect.h) && inRange(finish.first, texture_rect.x, texture_rect.w) && inRange(finish.second, texture_rect.y, texture_rect.h)) {
		pixels[start.first + start.second * texture_rect.w] = newPixels[finish.first + finish.second * texture_rect.w];
	}
}

double movementCompute(int transitionFrames, vector<pair<int, int>>& degree45, int r, SDL_Rect& texture_rect) {
	return 0.001 * r * transitionFrames * degree45.size();
}

void circularScreenEdit(int rstart, int rend, SDL_Rect texture_rect, int transitionFrames, Uint32* pixels, Uint32* newPixels, int maxRadius, SDL_PixelFormat* format, void (*perPixel)(Uint32*, Uint32*, vector<pair<int, int>>&, pair<int, int>&, SDL_Rect&, int, int, SDL_PixelFormat*, int, double), double (*compute)(int, vector<pair<int, int>>&, int r, SDL_Rect&)) {
	pair<int, int> center = {texture_rect.w / 2 + texture_rect.x, texture_rect.h / 2 + texture_rect.y};
	for (int r = rstart; r < rend; r += 1) {
		int xSquared = r * r;
		int makeCloser = (r - 1) * (r - 1);
		int change = 2 * r - 1;
		int x = r;
		int y = 0;
		vector<pair<int, int>> degree45;
		while (y <= x) {
			degree45.push_back({x, y});
			xSquared -= 2 * y + 1;
			if (xSquared <= makeCloser) {
				change -= 2;
				makeCloser -= change;
				x--;
				degree45.push_back({x, y});
			}
			y++;
		}
		double computedValue = compute(transitionFrames, degree45, r, texture_rect);
		for (int z = 0; z < 8 * degree45.size(); z++) {
			perPixel(pixels, newPixels, degree45, center, texture_rect, z, r, format, transitionFrames, computedValue);
		}
	}
}
```

This code, using the SDL2 library, will take the screen and make a spiralling effect using the pixels already on the screen. It is my favorite code snippet because of the clever usage of bitwise operators and integer mathematics to avoid doing heavy divisions and trignometric functions.

## Experience
As I said in [This section](#my-programming-journey), I do Python, Java and C++. I have also [made a game in one month called Naturogue](https://icegod9001.itch.io/naturogue). Below is a picture for reference.

[Naturogue](Naturogue.png)

Here are some other games I made
- Sea of Rogues
- Phantom Keys
- Ultra Sea Wars Rogue
- Ultra Sea Wars Elimination
- Aedox
- Kobold Master Alchemist (KMA)
- Petal Picker
- AJ Panic
- Control Panic
- Scuubie

Though many of these games are very bad and I will not link them. Here are the skills I have and ones that I want to improve on

- [x] Algorithmic optimization
- [ ] Documentation
- [x] Teamwork skills
- [ ] Usage of public and private
- [x] Quick and efficient coding
- [x] Good designer
- [x] Knowledge of UI/UX
- [ ] Broad range of experiences
- [ ] Database experience