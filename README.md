# Akshat Udyam Customer Support System

![License](https://img.shields.io/badge/license-MIT-blue.svg)
![Version](https://img.shields.io/badge/version-1.0.0-green.svg)
![Next.js](https://img.shields.io/badge/Next.js-15.0.0-black)
![TypeScript](https://img.shields.io/badge/TypeScript-5.0.0-blue)

A comprehensive customer support and management system for Akshat Udyam, a leading solar energy solutions provider. This platform offers a dual-interface system with separate portals for customers and administrators, enabling efficient management of support tickets, billing, installations, and customer communications. The system leverages an intent classification model powered by DistilBERT to enhance customer support automation.

![Akshat Udyam Dashboard](https://mega.nz/file/1z81EQwS#jVHnjLv4Q0ZnTWMnGCaLEvvDR-4HWUeWMdLaT18vYfQ)

## 🌟 Features

- **Customer Portal**
  - Support ticket management
  - Real-time chat support with intent-based responses
  - Billing and payment history
  - Solar system monitoring
  - Profile management
  - FAQ and knowledge base

- **Admin Portal**
  - Comprehensive dashboard with analytics
  - Customer management
  - Installation tracking
  - Invoice generation
  - Support ticket handling
  - Maintenance scheduling
  - Reporting tools

- **Shared Features**
  - Responsive design for all devices
  - Dark/light mode support
  - Real-time notifications
  - Secure authentication
  - Role-based access control
  - Intent classification for automated query handling (powered by DistilBERT)

## 📋 Prerequisites

Before you begin, ensure you have the following installed:
- [Node.js](https://nodejs.org/) (v18.0.0 or higher)
- [npm](https://www.npmjs.com/) (v8.0.0 or higher) or [yarn](https://yarnpkg.com/) (v1.22.0 or higher)
- [Git](https://git-scm.com/)
- Python 3.8+ (for intent classification model training)
- Required Python libraries: `torch`, `transformers`, `pandas`, `numpy`, `scikit-learn`, `matplotlib`, `seaborn`

## 🚀 Installation

1. Clone the repository:
   bash
   git clone https://github.com/your-username/akshat-udyam-support.git
   cd akshat-udyam-support
   

2. Install frontend dependencies:
   bash
   npm install
   # or
   yarn install
   

3. Set up the Python environment for intent classification:
   - Install Python dependencies:
     bash
     pip install torch transformers pandas numpy scikit-learn matplotlib seaborn
     
   - Place the Bitext dataset in `data/raw/Bitext_Sample_Customer_Service_Training_Dataset.csv`.

4. Configure environment variables:
   - Create a `.env.local` file in the root directory and add necessary variables (e.g., API keys, database URLs). Example:
     
     NEXT_PUBLIC_API_URL=http://localhost:3000/api
     DATABASE_URL=your_database_url
     

## 🛠 Usage

1. **Start the Development Server**:
   bash
   npm run dev
   # or
   yarn dev
   
   Open [http://localhost:3000](http://localhost:3000) to view the app.

2. **Train the Intent Classification Model**:
   - Run the training script:
     bash
     python scripts/train_intent_classifier.py
     
   - This generates a fine-tuned model saved in `models/distilbert-intent-classifier` and plots for loss, accuracy, and confusion matrix.

3. **Integrate Model with Frontend**:
   - The trained model can be used via an API endpoint (to be implemented) to classify customer queries in real-time chat support.

## 📂 Project Structure


akshat-udyam-support/
├── data/              # Dataset storage (e.g., Bitext CSV)
├── models/            # Saved intent classification models
├── scripts/           # Python scripts (e.g., train_intent_classifier.py)
├── src/               # Next.js application code
│   ├── pages/         # Next.js pages
│   ├── components/    # React components
│   ├── styles/        # CSS/Styled-Components
│   └── api/           # API routes
├── .env.local         # Environment variables
├── package.json       # Node.js dependencies
├── README.md          # This file
└── tsconfig.json      # TypeScript configuration


## 🔧 Development

- **Intent Classification**: The model is trained on a balanced dataset with intents like `ticket_query`, `scheduled_query`, `resolved_query`, and `cancel_order`. See `scripts/train_intent_classifier.py` for details.
- **Frontend**: Built with Next.js and TypeScript, featuring responsive design and real-time features.
- **Testing**: Add unit tests for components and API endpoints using Jest and React Testing Library.

## 📊 Results

- **Dataset**: 300 samples per intent after balancing.
- **Model Performance**: Visualized via training/validation loss, accuracy, and confusion matrix over 8 epochs.
- **Train/Validation Split**: 960 train samples, 240 validation samples, with minimized overlap.

## 🤝 Contributing

Contributions are welcome! Please fork the repository and submit a pull request with your changes. For major changes, open an issue first to discuss.

## 📜 License

This project is licensed under the [MIT License](LICENSE).

## 🙏 Acknowledgments

- [Hugging Face](https://huggingface.co/) for the `transformers` library.
- [Bitext](https://www.bitext.com/) for the sample customer service dataset.
- [Next.js](https://nextjs.org/) and [TypeScript](https://www.typescriptlang.org/) communities.

## Live preview link
[Click to check preview](https://v0.dev/chat/fork-of-customer-support-system-0yz1vaDaIoP)

### Notes:
- Replace https://github.com/your-username/akshat-udyam-support.git with your actual repository URL.
- Adjust the script file name (train_intent_classifier.py) and directory structure (scripts/) based on your project setup.
- Add a LICENSE file if not already present.
- The placeholder image URL (https://placeholder.com/dashboard-preview.png) should be replaced with an actual screenshot or removed if no image is available yet.
- I've integrated the intent classification details into the context of the customer support system, assuming the model enhances the chat support feature.
