# 🎭 Joke Generator Feature

A complete random joke generator using the **JokeAPI** external service for the My-work-flow-ai repository.

## ✨ Features

- 🎭 Fetch random jokes from 7 different categories
- 🔄 Support for single-liner and two-part jokes
- 📤 Share jokes with friends
- 🎯 Category selector with horizontal scroll
- ⚡ Loading states and error handling
- 🔒 TypeScript support for type safety
- 📱 Responsive React Native UI
- 🎨 Modern card-based design

## 📂 File Structure

```
src/
├── services/
│   └── jokeService.ts          # JokeAPI integration
├── hooks/
│   └── useJoke.ts              # Custom React hook
├── types/
│   └── jokes.ts                # TypeScript types
└── components/
    └── JokesScreen.tsx         # Main UI component
```

## 🎬 Quick Start

### Installation

```bash
# Clone and install
git clone https://github.com/zedpamphlets-web/My-work-flow-ai.git
cd My-work-flow-ai
npm install
```

### Integration

1. **Merge the feature branch:**
```bash
git checkout main
git pull origin main
git merge origin/feature/joke-generator
```

2. **Add to your navigation** (if using tabs):
```typescript
import JokesScreen from './src/components/JokesScreen';

// In your navigation:
<Stack.Screen name="Jokes" component={JokesScreen} />
```

3. **Use in your app:**
```typescript
import { useJoke } from './src/hooks/useJoke';

function MyComponent() {
  const { joke, loading, fetchJoke, categories } = useJoke();

  return (
    <View>
      {joke && <Text>{joke.text}</Text>}
      <TouchableOpacity onPress={() => fetchJoke('Programming')}>
        <Text>Get Joke</Text>
      </TouchableOpacity>
    </View>
  );
}
```

## 🗂️ Available Categories

- **Any** - Mix of all categories
- **Miscellaneous** - Variety of jokes
- **Programming** - Developer jokes
- **Knock-Knock** - Classic knock-knock jokes
- **General** - General humor
- **Spooky** - Halloween-themed jokes
- **Dark** - Dark humor

## 🔗 API Integration

### JokeAPI Details
- **Base URL:** `https://v2.jokeapi.dev/joke`
- **Free:** No authentication required
- **Docs:** https://jokeapi.dev/
- **Rate Limit:** Generous (safe for production)

### Example Request
```bash
curl https://v2.jokeapi.dev/joke/Programming
```

### Response Structure
```json
{
  "error": false,
  "category": "Programming",
  "type": "single",
  "joke": "Why do programmers prefer dark mode? Because light attracts bugs!",
  "flags": {
    "nsfw": false,
    "religious": false,
    "political": false,
    "racist": false,
    "sexist": false,
    "explicit": false
  }
}
```

## 🛠️ Hook Usage

```typescript
const {
  joke,              // Current joke object
  loading,           // Boolean - loading state
  error,             // String - error message
  fetchJoke,         // Function - get single joke
  fetchMultiple,     // Function - get multiple jokes
  clearJoke,         // Function - clear current joke
  categories         // Array - available categories
} = useJoke();
```

## 🎯 Components

### JokesScreen.tsx
Main component featuring:
- Header with title
- Category selector (horizontal scroll)
- Joke display card
- Action buttons (Get Joke, Share)
- Loading spinner
- Error messages
- Info section

## 🚀 Build & Deploy

### Development
```bash
npm start
```

### Build APK (Android)
```bash
eas build --platform android --type apk
```

### Build IPA (iOS)
```bash
eas build --platform ios
```

## 🐛 Troubleshooting

| Issue | Solution |
|-------|----------|
| No jokes loading | Check internet connection |
| API errors | Verify JokeAPI is accessible |
| Missing modules | Run `npm install` |
| Type errors | Ensure TypeScript is configured |

## 📝 License

MIT - Free to use and modify

## 🙏 Credits

- **JokeAPI** by Sv443 - Free joke API
- **React Native** - Mobile framework
- **TypeScript** - Type safety

## 🔮 Future Enhancements

- [ ] Favorite jokes
- [ ] Joke history
- [ ] Custom filters
- [ ] Offline caching
- [ ] Dark mode
- [ ] Analytics
- [ ] User ratings
- [ ] Search feature

---

**Ready to add laughs to your app!** 😂
