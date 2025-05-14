# QR Code Generator API

![QR Code](https://img.shields.io/badge/QR%20Code-Generator-blue)
![Spring Boot](https://img.shields.io/badge/Spring%20Boot-3.4.5-brightgreen)
![AWS S3](https://img.shields.io/badge/AWS-S3-orange)
![Java](https://img.shields.io/badge/Java-17-red)
![License](https://img.shields.io/badge/License-MIT-green)

A modern, high-performance QR code generation API built with Spring Boot that generates QR codes and automatically stores them in AWS S3.

## 🚀 Features

- **Simple API**: Generate QR codes with a single API call
- **Cloud Storage**: Automatic upload to AWS S3
- **Scalable Architecture**: Built with hexagonal architecture principles
- **Docker Ready**: Easily deploy with Docker
- **High Performance**: Optimized for speed and reliability

## 📋 Requirements

- Java 17 or higher
- Maven 3.6+
- AWS Account with S3 bucket
- Docker (optional)

## 🔧 Installation

### Option 1: Local Setup

1. Clone the repository
   ```bash
   git clone https://github.com/yourusername/qrcode-generator_aws_s3.git
   cd qrcode-generator_aws_s3
   ```

2. Configure AWS credentials
   Create a `.env` file with the following variables:
   ```
   AWS_BUCKET_NAME=your-bucket-name
   AWS_REGION=your-aws-region
   AWS_ACCESS_KEY_ID=your-access-key
   AWS_SECRET_ACCESS_KEY=your-secret-key
   ```

3. Build and run the application
   ```bash
   mvn clean install
   mvn spring-boot:run
   ```

### Option 2: Docker Setup

1. Build the Docker image
   ```bash
   docker build -t qrcode-generator_aws_s3:1.0 .
   ```
   docker build --build-arg AWS_ACCESS_KEY_ID=your-access-key \
                --build-arg AWS_SECRET_ACCESS_KEY=your-secret-key \
                -t qrcode-generator .
   ```

2. Run the container
   ```bash
   docker run --env-file .env -p 8080:8080 qrcode-generator_aws_s3:1.0
   ```
   docker run -p 8080:8080 qrcode-generator
   ```

## 🔌 API Usage

### Generate QR Code

**Endpoint:** `POST /qrcode`

**Request Body:**
```json
{
  "text": "https://example.com"
}
```

**Response:**
```json
{
  "url": "https://your-bucket-name.s3.your-region.amazonaws.com/generated-file-name"
}
```

## 🏗️ Architecture

The application follows a hexagonal architecture pattern:

- **Controller Layer**: Handles HTTP requests and responses
- **Service Layer**: Contains business logic for QR code generation
- **Port Layer**: Defines interfaces for external dependencies
- **Infrastructure Layer**: Implements external dependencies (AWS S3)

## 🛠️ Technology Stack

- **Spring Boot**: Web framework
- **ZXing**: QR code generation library
- **AWS SDK**: S3 integration
- **Maven**: Dependency management
- **Docker**: Containerization

## 🧪 Testing

Run the tests with Maven:

```bash
mvn test
```

## 📝 License

This project is licensed under the MIT License - see the LICENSE file for details.

## 👨‍💻 Author

- [Caio Reis](https://github.com/caior17)

## 🤝 Contributing

Contributions, issues, and feature requests are welcome!

1. Fork the project
2. Create your feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add some amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request
