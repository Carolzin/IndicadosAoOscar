# Indicados Ao Oscar 🏆

**Quantas vezes Natalie Portman foi indicada ao Oscar?**
R: 3 vezes.

Q:
```sql
SELECT COUNT(*) FROM indicados_ao_oscar WHERE nome_do_indicado Like "%Natalie Portman%";

```

**Quantos Oscars Natalie Portman ganhou?**
R: 1 vez.

Q:
```sql
SELECT COUNT(*) FROM indicados_ao_oscar
WHERE nome_do_indicado Like "%Natalie Portman%" AND vencedor = "true";
````

**Amy Adams já ganhou algum Oscar?**
R: Não.

Q:
```sql
SELECT * FROM indicados_ao_oscar WHERE nome_do_indicado  Like "%Amy Adams%";
```

**A série de filmes Toy Story ganhou um Oscar em quais anos?**
R: Sim, 2011, 2011 e 2020.

Q:

```sql
SELECT ano_cerimonia FROM indicados_ao_oscar WHERE nome_do_filme Like "%Toy Story%" AND vencedor = "true"
```

**A partir de que ano que a categoria "Actress" deixa de existir?**
R: 1976.

Q:
```sql
SELECT ano_cerimonia FROM indicados_ao_oscar WHERE categoria = 'Actress' ORDER BY ano_cerimonia DESC LIMIT 1;
```

**Quem ganhou o primeiro Oscar para Melhor Atriz? Em que ano?**
R: Marie-Christine Barrault em 1977.

Q: 
```sql
SELECT nome_do_indicado, ano_cerimonia FROM indicados_ao_oscar 
WHERE categoria = 'ACTRESS IN A LEADING ROLE' 
ORDER BY ano_cerimonia LIMIT 1;
```

**Na campo "Vencedor", altere todos os valores com "true" para 1 e todos os valores "false" para 0.**
Q:
```sql
UPDATE indicados_ao_oscar SET vencedor = 1 WHERE vencedor = 'true';
UPDATE indicados_ao_oscar SET vencedor = 0 WHERE vencedor = 'false';
```

**Em qual edição do Oscar "Crash" concorreu ao Oscar?**
R: 2006

Q:
```sql
SELECT ano_cerimonia FROM indicados_ao_oscar WHERE nome_do_filme Like "%Crash";
```

**O filme Central do Brasil aparece no Oscar?**
R: Não.

Q:
```sql
SELECT COUNT(*) > 0 FROM indicados_ao_oscar WHERE nome_do_filme Like "%Central do Brasil%";
```

**Inclua no banco 3 filmes que nunca foram nem nomeados ao Oscar, mas que merecem ser.**
```sql
INSERT INTO indicados_ao_oscar (ano_filmagem, ano_cerimonia, cerimonia, categoria, nome_do_indicado, nome_do_filme, vencedor) VALUES
(2009, 2010, '82nd Academy Awards', 'NONE', 'Coraline', 'Coraline', 'false'),
(2001, 2002, '74th Academy Awards', 'NONE', 'Harry Potter', 'Harry Potter and the Sorcerer\'s Stone', 'false'),
(2004, 2005, '77th Academy Awards', 'NONE', 'NONE', 'Scooby-Doo 2', 'Scooby-Doo 2: Monsters Unleashed', 'false');
```

**Denzel Washington já ganhou algum Oscar?**
R: Sim, 2.

Q:
```sql
SELECT COUNT(*) 
FROM indicados_ao_oscar
WHERE nome_do_indicado LIKE '%Denzel Washington%'
AND vencedor = 'true';
;
```


**Quais os filmes que ganharam o Oscar de Melhor Filme?**
R: Round Midnight, 20,000 Leagues under the Sea, 2001: A Space Odyssey, 7th Heaven, A Boy and His Dog, A Chance to Live, A Christmas Carol, A Close Shave, A Damsel in Distress, A Double Life, A Farewell to Arms, A Fish Called Wanda, A Free Soul, A Funny Thing Happened on the Way to the Forum, A Greek Tragedy, A Hole in the Head, A Letter to Three Wives, A Little Night Music, A Little Romance, A Man and a Woman, A Man for All Seasons, A Midsummer Night's Dream, A Passage to India, A Patch of Blue, A Place in the Sun, A Place to Stand, A River Runs through It, A Room with a View, A Shocking Accident, A Star Is Born, A Story of Healing, A Streetcar Named Desire, A Thousand Clowns, A Time for Justice, A Time Out of War, A Touch of Class, A Tree Grows in Brooklyn, A Year toward Tomorrow, Affliction, Air Force, Airport, Aladdin, Albert Schweitzer, Alexander's Ragtime Band, Alice Doesn't Live Here Anymore, Alien, Aliens, All about Eve, All about My Mother, All Quiet on the Western Front, All That Jazz, All That Money Can Buy, All the King's Men, All the President's Men, Almost Famous, Ama Girls, Amadeus, Amarcord, America America, American Beauty, American Dream, Amphibious Fighters, An American in Paris, An American Werewolf in London, An Occurrence at Owl Creek Bridge, An Officer and a Gentleman, Anastasia, Anchors Aweigh, Angel and Big Joe, Anna & Bella, Anna and the King of Siam, Anne Frank Remembered, Anne of the Thousand Days, Annie Get Your Gun, Annie Hall, Anthony Adverse, Antonia's Line, Apocalypse Now, Apollo 13, Aquatic House-Party, Arise, My Love, Around the World in 80 Days, Arthur, Arthur Rubinstein - The Love of Life, Artie Shaw: Time Is All You've Got, As Good as It Gets, Babe, Babette's Feast, Back to the Future, Bad Girl, Balance, Barry Lyndon, Batman, Battleground, Bear Country, Beauty and the Beast, Becket, Bedknobs and Broomsticks, Beetlejuice, Being There, Belle Epoque, Ben-Hur, Benjy, Best Boy, Beyond the Line of Duty, Big Mama, Bird, Birds Anonymous, Black and White in Color, Black Fox, Black Narcissus, Black Orpheus, Black Rider (Schwarzfahrer), Blithe Spirit, Blood and Sand, Blood on the Sun, Blossoms in the Dust, Blue Sky, Board and Care, Bob's Birthday, Body and Soul, Bonnie and Clyde, Bored of Education, Born Free, Born on the Fourth of July, Born Yesterday, Bound for Glory, Boys and Girls, Boys Don't Cry, Boys Town, Bram Stoker's Dracula, Braveheart, Breakfast at Tiffany's, Breaking Away, Breaking the Sound Barrier, Breathing Lessons: The Life and Work of Mark O'Brien, Broadway Melody of 1936, Broken Lance, Broken Rainbow, Bugsy, Bullets over Broadway, Bullitt, Bunny, Burnt by the Sun, Busy Little Bears, Butch Cassidy and the Sundance Kid, Butterfield 8, Butterflies Are Free, Cabaret, Cactus Flower, Calamity Jane, California Suite, Call Me Madam, Camelot, Captain Carey, U.S.A., Captains Courageous, Casablanca, Casals Conducts: 1964, Cat Ballou, Cavalcade, Chagall, Champion, Character, Charade, Chariots of Fire, Charly, Children of a Lesser God, Chinatown, Churchill's Island, Cimarron, Cinema Paradiso, Citizen Kane, City of Wax, City Slickers, Cleopatra, Climbing the Matterhorn, Close Encounters of the Third Kind, Close Harmony, Closed Mondays, Closely Watched Trains, Coal Miner's Daughter, Cocoon, Come and Get It, Come Back, Little Sheba, Coming Home, Common Threads: Stories from the Quilt, Cool Hand Luke, Coquette, Cover Girl, Crac, Crash Dive, Crashing the Water Barrier, Creature Comforts, Cries and Whispers, Cromwell, Crouching Tiger, Hidden Dragon, Cyrano de Bergerac, Czechoslovakia 1968, Dances With Wolves, Dangerous, Dangerous Liaisons, Dangerous Moves, Darling, Day for Night, Day of the Painter, Daybreak in Udi, Days of Heaven, Days of Waiting, Days of Wine and Roses, Dead Man Walking, Dead Poets Society, Deadly Deception: General Electric, Nuclear Weapons and Our Environment, Dear Diary, Death Becomes Her, Death on the Nile, December 7th, Declaration of Independence, Defending Our Lives, Der Fuehrer's Face, Dersu Uzala, Desert Victory, Design for Death, Designing Woman, Destination Moon, Dick Tracy, Dirty Dancing, Disraeli, Divorce--Italian Style, Doctor Dolittle, Doctor Zhivago, Dodsworth, Dog Day Afternoon, Don't, Down and Out in America, Dr. Jekyll and Mr. Hyde, Dr. Seuss' How the Grinch Stole Christmas, Driving Miss Daisy, Dumbo, Dylan Thomas, E.T. The Extra-Terrestrial, Earthquake, East of Eden, Easter Parade, Ed Wood, Educating Peter, Election Night (Valgaften), Elizabeth, Elmer Gantry, Emma, Erin Brockovich, Ersatz (The Substitute), Eskimo, Every Child, Evita, Exodus, Facing Your Danger, Fame, Fanny & Alexander, Fantastic Voyage, Fargo, Father and Daughter, Father Goose, Federico Fellini's 8-1/2, Fellini's Casanova, Ferdinand the Bull, Fiddler on the Roof, First Steps, Flamenco at 5:15, Flashdance, Flowers and Trees, For Scent-Imental Reasons, For Whom the Bell Tolls, Forrest Gump, Frank Film, Franz Kafka's It's a Wonderful Life, Frenchman's Creek, From Here to Eternity, From Mao to Mozart: Isaac Stern in China, Funny Girl, Gandhi, Gaslight, Gate of Hell, Genocide, Gentleman's Agreement, Gerald McBoing-Boing, Geri's Game, Get Out Your Handkerchiefs, Ghost, Giant, Gigi, Girl, Interrupted, Giuseppina, Give Me Liberty, Gladiator, Glass, Glory, Gods and Monsters, Going My Way, Gold Diggers of 1935, Goldfinger, Gone with the Wind, Good Fellas, Good Will Hunting, Good-bye Miss Turlock, Goodbye, Mr. Chips, Grand Canyon, Grand Hotel, Grand Prix, Grandad of Races, Gravity Is My Enemy, Great, Great Expectations, Green Dolphin Street, Guess Who's Coming to Dinner, Hamlet, Hannah and Her Sisters, Harlan County, U.S.A., Harry and the Hendersons, Harry and Tonto, Harvey, He Makes Me Feel Like Dancin', Hearts and Minds, Heaven Can Wait, Heavenly Music, Helen Keller in Her Story, Hello, Dolly!, Hello, Frisco, Hello, Henry V, Herb Alpert and the Tijuana Brass Double Feature, Here Comes Mr. Jordan, Here Comes the Groom, Heureux Anniversaire (Happy Anniversary), High Noon, Hitler Lives?, Holiday Inn, Hotel Terminus: The Life and Times of Klaus Barbie, How Green Was My Valley, How the West Was Won, How to Sleep, Howards End, Hud, I Am a Promise: The Children of Stanton Elementary School, I Want to Live!, I Wanted Wings, I Won't Play, I'll Cry Tomorrow, I'll Find a Way, If You Love This Planet, In Beaver Valley, In Old Arizona, In Old Chicago, In the Heat of the Night, In the Region of Ice, In the Shadow of the Stars, Independence Day, Indiana Jones and the Last Crusade, Indiana Jones and the Temple of Doom, Indochine, Innerspace, Interrupted Melody, Interviews with My Lai Veterans, Into the Arms of Strangers: Stories of the Kindertransport, Investigation of a Citizen above Suspicion, Iris, Irma La Douce, Is It Always Right to Be Right?, It Happened One Night, It's a Mad, Mad, Mad, Mad World, It's Tough to Be a Bird, Jacques-Yves Cousteau's World without Sun, Jaws, Jerry Maguire, Jezebel, JFK, Joan of Arc, Johann Mouse, Johnny Belinda, Johnny Eager, Journey into Self, Journey of Hope, Judgment at Nuremberg, Julia, Julius Caesar, Jurassic Park, Just Another Missing Kid, Karl Hess: Toward Liberty, Kentucky, Key Largo, King Gimp, King Kong, King of Jazz, King Solomon's Mines, Kiss of the Spider Woman, Kitty Foyle, Klute, Knighty Knight Bugs, Kokoda Front Line!, Kolya, Kon-Tiki, Krakatoa, Kramer vs. Kramer, L.A. Confidential, La Cucaracha, La Dolce Vita, La Strada, Lady Be Good, Laura, Lawrence of Arabia, Le Ciel et la Boue (Sky Above and Mud Beneath), Leave Her to Heaven, Leaving Las Vegas, Legends of the Fall, Leisure, Lend a Paw, Les Girls, Let It Be, Lieberman in Love, Life Is Beautiful, Light in the Window: The Art of Vermeer, Lili, Lilies of the Field, Limelight, Little Women, Logan's Run, Lost Horizon, Love Is a Many-Splendored Thing, Love Me or Leave Me, Love Story, Love You to Death, Love's Labour's Lost, Lover Come Back, Lovers and Other Strangers, Lucky Jim, Mad Max: Fury Road, Madame X, Maggie Smith: The Unseen Video, Mahogany, Make Way for Tomorrow, Maleficent, Maltese Falcon, Man of a Thousand Faces, Man of the West, Man on Fire, Man with a Movie Camera, Manchurian Candidate, Mary Poppins, Masquerade, Master and Commander: The Far Side of the World, Matinee, Maverick, McCabe & Mrs. Miller, Mean Streets, Meet Me in St. Louis, Meet the Robinsons, Men at Work, Merry Christmas, Mr. Lawrence, Metropolis, Midsummer Night's Dream, Midnight Cowboy, Midnight Express, Midway, Miracle on 34th Street, Mission: Impossible, Missing, Midsummer Night's Dream, Mississipi Burning, Moonstruck, More Than a Miracle, Moscow Does Not Believe in Tears, Mother Teresa: In My Own Words, Mr. Smith Goes to Washington, Mrs. Miniver, My Fair Lady, My Life as a Dog, My Name Is Nobody, My Neighbor Totoro, My Sister Eileen, My Sweet Little Village, National Velvet, Native Son, Naked City, Nashville, Neighbors, Never on Sunday, New York, New York, New York Stories, Night of the Hunter, Night Watch, No Country for Old Men, No Place Like Home, No Way Out, North by Northwest, Notorious, Nowhere to Go, O Brother, Where Art Thou?, Obsession, Ocean's Eleven, Of Mice and Men, Of Mice and Men, Of Mice and Men, Office Space, Oklahoma!, Old Yeller, Oliver Twist, On Dangerous Ground, On Golden Pond, On the Waterfront, Once Upon a Time in America, Once Upon a Time in the West, One Flew Over the Cuckoo's Nest, One Hundred and One Dalmatians, Open Hearts, Open Range, Operator, Orpheus, Orphan, Oscar and Lucinda, Out of Africa, Out of Sight, Our Town, Over the Edge, Othello, Our House, Paddington, Paddington 2, Paris, Texas, Paris, Je T'aime, Pastoral: To Die in the Country, Paths of Glory, Patton, Paul Robeson: Tribute to an Artist, Pay It Forward, Peeping Tom, Penny Serenade, Perfect Strangers, Phantom of the Opera, Philadelphia, Philadelphia Story, Piano, Picture Snatcher, Picture of Dorian Gray, Pillow Talk, Pinocchio, Pirates of the Caribbean: The Curse of the Black Pearl, Place of Peace, Planet of the Apes, Pleasantville, Plutonium Circus, Polar Express, Pollock, Pollock, Poltergeist, Porgy and Bess, Poseidon Adventure, Precious, Pretty Woman, Primary Colors, Prince of Tides, Private Benjamin, Private Ryan, Producer's Cut, Promises, Pumpkinhead, Pulp Fiction, Purple Rain, Quo Vadis, Rain Man, Raise the Red Lantern, Raiders of the Lost Ark, Ralph Bunche: An American Odyssey, Raging Bull, Rainbow, Ransom, Ratatouille, Real Genius, Rear Window, Rebel Without a Cause, Red River, Red-Headed Woman, Redacted, Remember the Titans, Reminiscence, Reservoir Dogs, Resurrection, Return of the Jedi, Return to Paradise, Ride the High Country, Right of Way, River of No Return, Road to Perdition, Road to Singapore, Rob Roy, Rocky, Roman Holiday, Room at the Top, Rope, Rose Marie, Rosemary's Baby, Runaway Jury, Runaway Train, Rushmore, S.W.A.T., Sabrina, Sabrina, Scent of a Woman, Schindler's List, School Ties, Scrooged, Search for Paradise, Searching for Bobby Fischer, Searching for Debra Winger, Second-Hand Lions, Secrets of the Heart, See You in the Morning, Sense and Sensibility, Seven Days in May, Seven Samurai, Sex, Lies, and Videotape, Shadow of a Doubt, Shadows, Shaolin Soccer, Shallow Grave, Shakespeare in Love, Shark Tale, Shawshank Redemption, She Done Him Wrong, She Wore a Yellow Ribbon, Sheena, Shine, Shine a Light, Ship of Fools, Shutter Island, Silent Night, Deadly Night, Silent Night, Deadly Night, Sin City, Singing in the Rain, Six Degrees of Separation, Six Feet Under, Slumdog Millionaire, Snow Falling on Cedars, Some Like It Hot, Something's Gotta Give, Son of Paleface, Song of the South, Sorcerer, Sound of Music, South Pacific, Space Jam, Special Bulletin, Species, Species II, Spirit of the Wind, Spider-Man, Spirited Away, Spotlight, Spotlight, Spontaneous, Spooky, Spouse, Spring, Spy Game, Stage Door, Stand by Me, Stand Up Guys, Star Wars, Star Wars: Episode I - The Phantom Menace, Star Wars: Episode II - Attack of the Clones, Star Wars: Episode III - Revenge of the Sith, Starship Troopers, Steel Magnolias, Stealing Home, Step Up, Steven Spielberg: A Director's Tribute, Still Alice, Still Crazy, Still Life, Still Life, Still Mine, Stillwater, Stolen Lives, Stop Making Sense, Stop-Loss, Story of the Weeping Camel, Strange Cargo, Stranger than Fiction, Stranger on a Train, Strangers on a Train, Strangelove, Strangers with Candy, Studio 54, Such a Beautiful Day, Sullivan's Travels, Summer of Sam, Summer Stock, Summer, Sunshine, Superhero Movie, Surfer, Suspicion, Sweet Bird of Youth, Sweet Smell of Success, Sweetheart, Sweetie, Swing Time, Synecdoche, New York, T2: Trainspotting, Taffy, Take the Money and Run, Taken, Talladega Nights: The Ballad of Ricky Bobby, Tangled, Tales from the Crypt, Tarzan, Taxi Driver, Tea with Mussolini, Tender Mercies, Terms of Endearment, Thank You for Smoking, That Darn Cat, That Thing You Do!, The 39 Steps, The Absent-Minded Professor, The Adventures of Ichabod and Mr. Toad, The Adventures of Robin Hood, The African Queen, The Age of Innocence, The Alamo, The Alchemist, The Amazing Race, The Amazing Spider-Man, The Amityville Horror, The American President, The Andromeda Strain, The Apartment, The Aristocats, The Artist, The Assassin, The Assassination of Jesse James by the Coward Robert Ford, The Atonement, The Awful Truth, The Band Wagon, The Barbarian and the Geisha, The Beach, The Bear, The Big Heat, The Big Knife, The Big Sleep, The Birdcage, The Birds, The Black Stallion, The Blind Side, The Boondock Saints, The Box, The Bridge on the River Kwai, The Brothers Karamazov, The Bucket List, The Caine Mutiny, The Candidate, The Canterville Ghost, The Canyons, The Castle, The Cat in the Hat, The Chase, The Children, The City of Lost Children, The Clouded Yellow, The Color Purple, The Conversation, The Constant Gardener, The Count of Monte Cristo, The Croods, The Curious Case of Benjamin Button, The Curse of the Were-Rabbit, The Da Vinci Code, The Dark Knight, The Dark Tower, The Day After Tomorrow, The Day the Earth Stood Still, The Dead Zone, The Deer Hunter, The Departed, The Devil and Daniel Webster, The Devil Wears Prada, The Diary of Anne Frank, The Discreet Charm of the Bourgeoisie, The Distance Between Us, The Divine Secrets of the Ya-Ya Sisterhood, The Doctor, The Doors, The Double Life of Véronique, The Double Life of Harry Houdini, The Double Life of Oscar Wilde, The Dreamers, The Elephant Man, The English Patient, The Exorcist, The Expendables, The Fabulous Baker Boys, The Farewell Party, The Fifth Element, The Fighting Seabees, The Fighter, The Fisher King, The Florida Project, The Fly, The Fountain, The French Connection, The French Dispatch, The Fugitive, The Girl with the Dragon Tattoo, The Giver, The Gnome-Mobile, The Good Girl, The Good Son, The Graduate, The Great Escape, The Great Gatsby, The Great Santini, The Great Wall, The Green Mile, The Green Years, The Gritty City, The Grudge, The Hangover, The Haunting, The Help, The Hero, The Hunger Games, The Hustler, The Imitation Game, The Incredibles, The Incredible Hulk, The Informant!, The Iron Lady, The Iron Giant, The Italian Job, The Jazz Singer, The Kid, The Kid Stays in the Picture, The Killing, The King's Speech, The Last Emperor, The Last Picture Show, The Last Samurai, The Last Waltz, The Lego Movie, The Lion in Winter, The Lion King, The Little Prince, The Living Daylights, The Longest Yard, The Lost Boys, The Lost Weekend, The Love Bug, The Magic Flute, The Man in the Iron Mask, The Man Who Knew Too Much, The Man Who Would Be King, The Mask of Zorro, The Matrix, The Matrix Reloaded, The Matrix Revolutions, The Melancholy of Haruhi Suzumiya, The Midnight Sky, The Miracle of Morgan's Creek, The Miracle of Our Lady of Fatima, The Missing Person, The Mission, The Misfits, The Muppet Movie, The Naked and the Dead, The Naked Gun, The Naked Jungle, The Nightmare Before Christmas, The Notebook, The Nutty Professor, The Other Woman, The Others, The Outsiders, The Overnighters, The Parent Trap, The Passion of the Christ, The Perfect Storm, The Persuaders!, The Phantom Menace, The Philadelphia Story, The Pianist, The Pink Panther, The Player, The Polar Express, The Prestige, The Prince of Egypt, The Princess Bride, The Producers, The Pursuit of Happyness, The Queen, The Queen of Versailles, The Railway Man, The Revenant, The Right Stuff, The Road to El Dorado, The Road to Perdition, The Secret in Their Eyes, The Secret Life of Pets, The Secret Life of Walter Mitty, The Shape of Water, The Shawshank Redemption, The Shop Around the Corner, The Silence of the Lambs, The Simpsons Movie, The Singularity Is Near, The Sixth Sense, The Social Network, The Sound of Music, The Spy Who Came in from the Cold, The Stepfather, The Straight Story, The Sum of All Fears, The Sweet Hereafter, The Sweet Life, The Tale of the Princess Kaguya, The Terminal, The Thing, The Three Musketeers, The Time Machine, The Time Traveler's Wife, The Town, The Treasure of the Sierra Madre, The Trial, The Truth About Cats & Dogs, The Truth About Charlie, The Truth About Dogs, The Truth About Love, The Truth, The Ugly Duckling, The Unbearable Lightness of Being, The Uninvited, The Usual Suspects, The Valley of the Dolls, The Vicious Kind, The Virgin Suicides, The Visit, The Walk, The War of the Roses, The Waterboy, The Way We Were, The Wedding Singer, The Wild Bunch, The Wind and the Willows, The Wizard of Oz, The Wolf of Wall Street, The Wrecking Crew, The Year of Living Dangerously, The Young Victoria, Their Eyes Were Watching God, There Will Be Blood, These Three, This Boy's Life, This Is Spinal Tap, This Is Us, This Is Where I Leave You, This Is the End, This Property Is Condemned, Three Blind Mice, Three Colors: Blue, Three Colors: Red, Three Colors: White, Three Days of the Condor, Three Little Pigs, Three to Tango, Three Women, Ticket to Paradise, Tidal Wave, Ties That Bind, To Kill a Mockingbird, To the Wonder, To Wong Foo, Thanks for Everything! Julie Newmar, Tom and Jerry: The Mansion Cat, Tomb Raider, Tomcats, Tommy, Top Gun, Top Hat, Total Recall, Touch of Evil, Tower of Terror, Town and Country, Toy Story, Toy Story 2, Toy Story 3, Toy Story 4, Traffic, Trainspotting, True Grit, True Lies, True Romance, Truman, Troy, Tusk, Twelve Monkeys, Twister, Two for the Money, Two Mules for Sister Sara, Two Night Stand, Two Women, U-571, Ulysses, Unforgiven, Unfinished Song, Unstoppable, Up, Up Close and Personal, Up the Yangtze, V for Vendetta, Vicious, Vietnam: A Television History, Vigilante Force, Village of the Damned, Virtuosity, Viva Las Vegas, Wall Street, Walkabout, Wallace & Gromit: The Curse of the Were-Rabbit, War Horse, War of the Roses, War of the Worlds, Washington's Crossing, Water for Elephants, Water Lilies, Watership Down, Way Down East, Wayne's World, We Are Marshall, We Were Soldiers, Weiner, Welcome to Mooseport, West Side Story, What Dreams May Come, What Happened to Baby Jane?, What Lies Beneath, What We Do in the Shadows, When Harry Met Sally..., When Marnie Was There, Where the Red Fern Grows, Whiplash, White Christmas, White House Down, White Noise, Who Framed Roger Rabbit, Who's Afraid of Virginia Woolf?, Who's Killing the Great Chefs of Europe?, Why We Fight, Willard, Willy Wonka & the Chocolate Factory, Winning Time: The Rise of the Lakers Dynasty, Win Win, Winter's Bone, Wives of the Skies, Wolf Hall, Woman on the Verge of a Nervous Breakdown, Wonder Woman, Wonderstruck, World War Z, Wreck-It Ralph, Wreck-It Ralph 2, Wuthering Heights, X-Men, X-Men: Days of Future Past, X-Men: The Last Stand, You Again, You Can't Take It with You, You Don't Mess with the Zohan, You Got Served, Your Name, Z, Zathura: A Space Adventure, Zelig, Zero Dark Thirty.

Q: 
```sql
SELECT DISTINCT nome_do_filme FROM indicados_ao_oscar WHERE vencedor = 'True';

``` 

**Bonus: Denzel Washington e Jamie Foxx já concorreram ao Oscar no mesmo ano?**
R: Sim, em 2017.

```sql
SELECT DISTINCT ano_cerimonia 
FROM indicados_ao_oscar
WHERE (nome_do_indicado LIKE '%Denzel Washington%' OR nome_do_indicado LIKE '%Jamie Foxx%')
GROUP BY ano_cerimonia
HAVING COUNT(DISTINCT nome_do_indicado) > 1;
```
