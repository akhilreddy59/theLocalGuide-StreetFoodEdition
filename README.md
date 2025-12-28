# 🍜 Local Street Food Recommender

A smart, context-aware street food recommendation system that helps you discover the best local street food based on your preferences for area, time of day, and audience type. Built specifically for Hyderabad's vibrant street food scene.

## 🌟 Features

- **Smart Recommendations**: Intelligent filtering based on area, time, and audience preferences
- **Comprehensive Database**: 100+ street food items across 30+ areas in Hyderabad
- **Fallback Logic**: Provides alternative suggestions when exact matches aren't found
- **Responsive Design**: Works seamlessly on desktop and mobile devices
- **Real-time Filtering**: Instant recommendations without loading delays
- **Rich Information**: Detailed food cards with pricing, timing, vibe, and local insights
- **Context-Aware**: Uses local knowledge and cultural insights for authentic recommendations

## 🚀 Quick Start

### Prerequisites

- **Node.js** (version 14 or higher)
- **npm** or **yarn** package manager

### Installation

1. **Clone the repository**
   ```bash
   git clone <repository-url>
   cd street-food-recommender
   ```

2. **Install dependencies**
   ```bash
   npm install
   ```

3. **Start the development server**
   ```bash
   npm start
   ```

4. **Open your browser**
   Navigate to [http://localhost:3000](http://localhost:3000)

## 🏗️ Project Structure

```
street-food-recommender/
├── public/
│   ├── product.md              # Street food data source
│   └── index.html              # HTML template
├── src/
│   ├── components/
│   │   ├── filters/            # Filter components
│   │   │   ├── FilterPanel.tsx
│   │   │   ├── AreaSelector.tsx
│   │   │   ├── TimeSelector.tsx
│   │   │   └── AudienceSelector.tsx
│   │   └── recommendations/    # Recommendation display components
│   │       ├── RecommendationList.tsx
│   │       └── FoodCard.tsx
│   ├── hooks/                  # Custom React hooks
│   │   ├── useProductContext.ts
│   │   └── useRecommendations.ts
│   ├── services/               # Business logic services
│   │   ├── contextParser.ts
│   │   ├── contextParser.test.ts
│   │   └── recommendationEngine.ts
│   ├── types/                  # TypeScript type definitions
│   │   └── index.ts
│   ├── data/                   # Local data files
│   │   └── product.md
│   ├── App.tsx                 # Main application component
│   ├── App.css                 # Application styles
│   └── index.tsx               # Application entry point
├── .kiro/                      # Specification documents
│   └── specs/street-food-recommender/
│       ├── requirements.md
│       ├── design.md
│       └── tasks.md
├── package.json
└── README.md
```

## 🎯 How to Use

### 1. **Select Your Preferences**
- **Area**: Choose from 30+ areas like Charminar, Gachibowli, Hitech City, etc.
- **Time of Day**: Pick from Morning, Afternoon, Evening, Late Night, etc.
- **Audience Type**: Select Students, Families, IT Workers, Couples, etc.

### 2. **Get Recommendations**
- View personalized street food suggestions based on your filters
- Each recommendation includes detailed information about the food item

### 3. **Explore Details**
Each food card displays:
- **Name**: The street food item name
- **Area**: Location where it's available
- **Price Range**: Low, Medium, or High
- **Best Time**: Optimal time to visit
- **Perfect For**: Target audience
- **Vibe**: Atmosphere and experience
- **Must Try**: Specific recommendations
- **Notes**: Local insights and tips

### 4. **Clear Filters**
- Use the "Clear All Filters" button to reset and see all available options

## 🛠️ Available Scripts

### Development

```bash
# Start development server
npm start

# Run tests
npm test

# Run tests without watch mode
npm test -- --watchAll=false

# Build for production
npm run build

# Serve production build locally
npm run serve
```

### Testing

The project includes comprehensive testing:
- **Unit Tests**: Test individual components and functions
- **Property-Based Tests**: Test universal properties using fast-check
- **Integration Tests**: Test complete user workflows

```bash
# Run all tests
npm test

# Run tests with coverage
npm test -- --coverage

# Run specific test file
npm test contextParser.test.ts
```

## 🏛️ Architecture

### **Frontend Architecture**
- **React 18** with TypeScript for type safety
- **Custom Hooks** for state management and business logic
- **Component-based architecture** with clear separation of concerns
- **CSS-in-JS** styling with responsive design

### **Data Flow**
1. **Data Loading**: `useProductContext` hook loads and parses street food data
2. **Filtering**: `useRecommendations` hook applies filters using the recommendation engine
3. **Display**: Components render filtered results with rich information

### **Key Services**
- **Context Parser**: Converts markdown data into structured objects
- **Recommendation Engine**: Handles filtering, scoring, and fallback logic
- **Type System**: Comprehensive TypeScript types for data integrity

## 📊 Data Format

The application uses a custom markdown format for street food data:

```markdown
Locations
Area: [Area Name]
Foods:

Name: [Food Name]
Audience: [Comma-separated audience types]
Price: [Low/Medium/High]
Time: [Time slots]
Vibe: [Description of atmosphere]
MustTry: [Specific recommendations]
Notes: [Local insights and tips]
```

### **Adding New Data**
To add new street food items:
1. Edit `public/product.md`
2. Follow the existing format
3. Restart the development server

## 🧪 Testing Strategy

### **Property-Based Testing**
The project uses property-based testing to ensure correctness:
- **Context Parsing**: Validates data parsing across various input formats
- **Filtering Logic**: Tests recommendation engine with generated data
- **UI Reactivity**: Ensures consistent behavior across user interactions

### **Test Coverage**
- Context parsing and data validation
- Recommendation engine logic
- Component rendering and user interactions
- Error handling and edge cases

## 🚀 Deployment

### **Production Build**
```bash
npm run build
```

### **Deployment Options**
- **Netlify**: Deploy the `build` folder
- **Vercel**: Connect your repository for automatic deployments
- **GitHub Pages**: Use `gh-pages` package for GitHub hosting
- **AWS S3**: Upload build files to S3 bucket with static hosting

### **Environment Variables**
No environment variables required for basic functionality.

## 🔧 Configuration

### **Customization Options**
- **Data Source**: Modify `public/product.md` to change street food data
- **Styling**: Update `src/App.css` for visual customization
- **Areas**: Add new areas by updating the data file
- **Time Slots**: Extend time options in `src/types/index.ts`

### **Performance Optimization**
- Data is loaded once and cached in memory
- Filtering is performed synchronously for instant results
- Components are optimized to prevent unnecessary re-renders

## 🤝 Contributing

### **Development Setup**
1. Fork the repository
2. Create a feature branch: `git checkout -b feature-name`
3. Make your changes
4. Run tests: `npm test`
5. Commit changes: `git commit -m 'Add feature'`
6. Push to branch: `git push origin feature-name`
7. Submit a pull request

### **Code Standards**
- Use TypeScript for all new code
- Follow existing component patterns
- Write tests for new functionality
- Maintain responsive design principles

## 📝 Specification Documents

The project follows spec-driven development with comprehensive documentation:
- **Requirements**: `.kiro/specs/street-food-recommender/requirements.md`
- **Design**: `.kiro/specs/street-food-recommender/design.md`
- **Tasks**: `.kiro/specs/street-food-recommender/tasks.md`

## 🐛 Troubleshooting

### **Common Issues**

**Data not loading:**
- Check that `public/product.md` exists and is properly formatted
- Verify the development server is running

**Filters not working:**
- Clear browser cache and reload
- Check browser console for JavaScript errors

**Build failures:**
- Run `npm install` to ensure all dependencies are installed
- Check for TypeScript errors: `npm run build`

### **Performance Issues**
- The app is optimized for instant filtering
- If experiencing slowness, check browser developer tools for performance bottlenecks

## 📄 License

This project is open source and available under the [MIT License](LICENSE).

## 🙏 Acknowledgments

- Built with **Create React App** and **TypeScript**
- Uses **fast-check** for property-based testing
- Inspired by Hyderabad's incredible street food culture
- Developed using spec-driven development methodology

## 📞 Support

For questions, issues, or contributions:
- Open an issue on GitHub
- Check the specification documents for detailed requirements and design
- Review the test files for usage examples

---

**Made with ❤️ for street food lovers**