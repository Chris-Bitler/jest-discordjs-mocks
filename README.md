# Jest Discord.js Mocks
A bunch of mocks that can be used in place for various discord.js classes for unit testing with Jest.


## Usage
You can import the Mock classes for the discord.js class that you are trying to mock out, such as `MockMessage`

From there, you can set various properties and replace methods with jest.fn() calls.

Example:
```typescript
import {MockMessage, MockTextChannel} from "jest-discordjs-mocks";

test("discord.js mock test", () => {
    const message = new MockMessage();
    const channel = new MockTextChannel();
    message.content = "test";
    message.channel = channel;
    callMyFunctionToTestHere(message);
    expect(message.channel.send).toHaveBeenCalled()
});
```
## Why some classes are exported and some aren't
Jest only allows for mocking certain classes from discord.js in typescript - the rest will result in errors