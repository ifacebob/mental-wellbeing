MindfulBalance - AI-Powered Mental Wellness Platform
Project Overview

MindfulBalance is a comprehensive mental wellness platform that combines two AI-powered tools to support student mental health and academic success. The platform addresses UN Sustainable Development Goal 3: Good Health and Well-being by providing accessible mental health support through innovative technology.
Features
1. AI Mood Journal

    Daily emotion tracking with sentiment analysis

    Mood rating system (1-10 scale)

    AI-powered emotional pattern recognition

    Interactive mood visualization charts

    Journal entry history and trends

2. AI Study Buddy

    Flashcard generation from study notes

    Interactive flip-card learning system

    Spaced repetition techniques

    Study progress tracking

    Personalized learning recommendations

Technology Stack
Frontend

    HTML5: Semantic structure and accessibility

    CSS3: Responsive design with Flexbox and Grid

    JavaScript: Interactive functionality and API integration

    Chart.js: Data visualization for mood tracking

Backend (Simulated in this demo)

    Python Flask: RESTful API endpoints

    MySQL: Data storage for user entries and flashcards

    Hugging Face API: AI sentiment analysis and question generation

AI Integration

    Sentiment Analysis: Emotion detection from journal entries

    Question Generation: Automatic flashcard creation from study notes

Project Structure
text

mindfulbalance/
├── index.html          # Main application page
├── styles.css          # All styling and responsive design
├── script.js           # Application functionality and interactions
├── README.md           # Project documentation
└── assets/             # Images and additional resources

Installation & Setup
Prerequisites

    Modern web browser with JavaScript enabled

    Web server for deployment (optional for local testing)

Local Development

    Clone or download the project files

    Open index.html in a web browser

    The application will run fully client-side

Production Deployment

    Upload all files to a web server

    Ensure proper MIME types for CSS and JS files

    For backend integration, set up Flask API endpoints

Usage Guide
Mood Journal

    Navigate to the Mood Journal page

    Select a date or use today's date

    Write about your feelings in the text area

    Rate your mood on a scale of 1-10

    Click "Analyze My Mood" to get AI insights

    View your mood history and trends on the chart

Study Buddy

    Navigate to the Study Buddy page

    Enter a topic for your study session

    Paste or type your study notes

    Click "Generate Flashcards" to create interactive cards

    Click on flashcards to flip them and reveal answers

    Use the study tips for effective learning techniques

API Integration (For Full Implementation)
Mood Analysis Endpoint
python

# Flask route for sentiment analysis
@app.route('/api/analyze-mood', methods=['POST'])
def analyze_mood():
    journal_text = request.json['text']
    # Call Hugging Face sentiment analysis API
    sentiment = hugging_face_sentiment(journal_text)
    return jsonify(sentiment)

Flashcard Generation Endpoint
python

# Flask route for question generation
@app.route('/api/generate-questions', methods=['POST'])
def generate_questions():
    study_text = request.json['text']
    # Call Hugging Face question generation API
    questions = hugging_face_qg(study_text)
    return jsonify(questions)

Database Schema (For Full Implementation)
Users Table
sql

CREATE TABLE users (
    id INT AUTO_INCREMENT PRIMARY KEY,
    username VARCHAR(50) UNIQUE NOT NULL,
    email VARCHAR(100) UNIQUE NOT NULL,
    created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP
);

Journal Entries Table
sql

CREATE TABLE journal_entries (
    id INT AUTO_INCREMENT PRIMARY KEY,
    user_id INT,
    entry_date DATE NOT NULL,
    content TEXT NOT NULL,
    mood_rating INT,
    sentiment_score FLOAT,
    created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP,
    FOREIGN KEY (user_id) REFERENCES users(id)
);

Flashcards Table
sql

CREATE TABLE flashcards (
    id INT AUTO_INCREMENT PRIMARY KEY,
    user_id INT,
    topic VARCHAR(255) NOT NULL,
    question TEXT NOT NULL,
    answer TEXT NOT NULL,
    created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP,
    FOREIGN KEY (user_id) REFERENCES users(id)
);

Responsive Design

The application is fully responsive and optimized for:

    Mobile devices (320px and up)

    Tablets (768px and up)

    Desktops (1024px and up)

    Large screens (1200px and up)

Browser Compatibility

    Chrome (60+)

    Firefox (60+)

    Safari (12+)

    Edge (79+)

Future Enhancements

    User Authentication: Secure login system

    Data Persistence: Cloud storage for user data

    Advanced Analytics: Detailed insights and recommendations

    Social Features: Community support and sharing

    Mobile App: Native iOS and Android applications

    Integration: Calendar and productivity tool integration

Contributing

    Fork the repository

    Create a feature branch (git checkout -b feature/amazing-feature)

    Commit your changes (git commit -m 'Add amazing feature')

    Push to the branch (git push origin feature/amazing-feature)

    Open a Pull Request

License

This project is licensed under the MIT License - see the LICENSE file for details.
Acknowledgments

    UN Sustainable Development Goals framework

    Hugging Face for AI API services

    Unsplash for provided images

    Font Awesome for icons

    Google Fonts for typography

Support

For support or questions about this project, please contact:

    Email: support@mindfulbalance.com

    Website: www.mindfulbalance.com

Demo Notes

This is a frontend demonstration of the MindfulBalance platform. In a full implementation, the Python Flask backend would handle:

    User authentication and data persistence

    Integration with Hugging Face AI APIs

    Database operations for storing user entries and flashcards

    Server-side validation and security measures

The current demo simulates these functionalities client-side for presentation purposes.
