# PhantomHunt

PhantomHunt is an asymmetric 2D multiplayer game built for the University of Basel CS108 programming project. Four players enter a haunted castle: one human tries to survive, while three phantoms coordinate to hunt them down.

![PhantomHunt gameplay screenshot](documentations/images/Phantom-Hunt_game.png)

## Features

- Asymmetric 3-vs-1 multiplayer rounds with rotating roles.
- JavaFX client with lobby creation, joining, chat, spectating, high scores, and configurable key bindings.
- TCP server that manages players, lobbies, rounds, scoring, and game-state broadcasts.
- Tile-based castle map with collision handling, animated sprites, sound effects, ambient music, and ability pickups.
- Four-round matches where every player gets one turn as the human.

## Gameplay

The human earns points by surviving and can use abilities to escape pressure. Phantoms earn points by finding and catching the human. After four rounds, the player with the highest total score wins.

Additional gameplay and project material from the original course submission is kept in `documentations/` and `outreach/`.

## Tech Stack

- Java 25
- Gradle with the Gradle Wrapper
- JavaFX 25
- LWJGL / OpenAL for audio
- Log4j 2
- JUnit 5, Mockito, and JaCoCo for tests and coverage

## Requirements

- JDK 25 or a compatible Java toolchain available to Gradle
- A terminal for starting the server and clients
- Network access between the server host and client machines for multiplayer games

## Build

From the repository root:

```bash
./gradlew jar
```

The executable jar is written to:

```text
build/libs/phantom-hunt.jar
```

Run the full build and tests with:

```bash
./gradlew build
```

## Run

Start one server:

```bash
java -jar build/libs/phantom-hunt.jar server 2222
```

Start each client with the server address:

```bash
java -jar build/libs/phantom-hunt.jar client localhost:2222
```

You can also pass a nickname as a third argument:

```bash
java -jar build/libs/phantom-hunt.jar client localhost:2222 PlayerName
```

Use the host machine's LAN IP address instead of `localhost` when clients connect from other machines.

## Controls

| Action | Default keyboard control |
| --- | --- |
| Move up | `W` |
| Move left | `A` |
| Move down | `S` |
| Move right | `D` |
| Wisdom Blessing, when available | `R` |
| Toggle fullscreen | `F11` or `F` |

Movement keys can be changed in the in-game key binding screen.

## Project Structure

```text
src/main/java/        Game, client, server, protocol, JavaFX UI, and audio code
src/main/resources/   Runtime assets, audio, intro video, and Log4j config
src/test/java/        Unit and integration tests
documentations/       Original project documentation, manual, diagrams, and asset sources
outreach/             Original course outreach page and media assets
gradle/wrapper/       Gradle Wrapper files
```

## Team

- Jan Haag
- Hermes Reisner
- Vera Bitterlin
- Silas Weber
- Ismail Djemaili

See [CONTRIBUTORS.md](CONTRIBUTORS.md) for the contributor list.

## License

This project is licensed under the MIT License. See [LICENSE](LICENSE) for details.
