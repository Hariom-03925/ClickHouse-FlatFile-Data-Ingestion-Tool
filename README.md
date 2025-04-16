# ClickHouse-FlatFile Data Ingestion Tool

A web-based application for bidirectional data ingestion between ClickHouse databases and flat files (CSV).

![Project Banner](docs/images/banner.png)

## Features

- **Bidirectional Data Flow**: Export data from ClickHouse to flat files and import data from flat files to ClickHouse
- **JWT Authentication**: Secure connection to ClickHouse using JWT tokens
- **Column Selection**: Choose specific columns for data ingestion
- **Data Preview**: Preview data before ingestion (limited to 100 records)
- **Progress Tracking**: Monitor the progress of long-running ingestion tasks
- **Multi-Table Join**: Join multiple ClickHouse tables and export the results

## Tech Stack

- **Backend**: Java Spring Boot
- **Frontend**: React with Material-UI
- **Database**: ClickHouse
- **Authentication**: JWT

## Screenshots

### ClickHouse to File Export
![ClickHouse to File](docs/images/clickhouse-to-file.png)

### File to ClickHouse Import
![File to ClickHouse](docs/images/file-to-clickhouse.png)

### Multi-Table Join
![Join Tables](docs/images/join-tables.png)

## Prerequisites

- Java 17+
- Maven 3.8+
- Node.js 14+
- Docker (for local ClickHouse instance)

## Quick Start

### Backend Setup

```bash
cd backend
mvn clean install
mvn spring-boot:run
```

### Frontend Setup

```bash
cd frontend
npm install
npm start
```

### ClickHouse Setup

```bash
docker run -d --name clickhouse-server -p 8123:8123 -p 9000:9000 clickhouse/clickhouse-server
```

## Documentation

For detailed documentation, please refer to:
- [Project Documentation](docs/project-documentation.md)
- [API Documentation](docs/api-documentation.md)
- [User Guide](docs/user-guide.md)

## Project Structure

```
.
├── backend/                 # Spring Boot backend
│   ├── src/                # Source code
│   │   ├── main/           # Main application code
│   │   └── test/           # Test code
│   └── pom.xml             # Maven configuration
├── frontend/               # React frontend
│   ├── src/                # Source code
│   │   ├── components/     # React components
│   │   ├── pages/          # Page components
│   │   └── services/       # API services
│   └── package.json        # NPM configuration
├── docs/                   # Documentation
│   ├── images/             # Screenshots and images
│   ├── project-documentation.md  # Project documentation
│   └── api-documentation.md      # API documentation
└── README.md               # This file
```

## API Endpoints

| Endpoint | Method | Description |
|----------|--------|-------------|
| `/api/tables` | GET | Get list of tables from ClickHouse |
| `/api/columns` | GET | Get columns for a specific table |
| `/api/preview/clickhouse` | GET | Preview data from ClickHouse |
| `/api/preview/file` | GET | Preview data from a file |
| `/api/ingest/clickhouse-to-file` | POST | Export data from ClickHouse to file |
| `/api/ingest/file-to-clickhouse` | POST | Import data from file to ClickHouse |
| `/api/ingest/join-tables` | POST | Join multiple tables and export results |

## Testing

The application includes comprehensive testing for:
- Single table ingestion
- Flat file to ClickHouse import
- Multi-table joins
- Authentication and connection handling
- Data preview functionality
- Progress tracking
- Error handling scenarios

## Contributing

1. Fork the repository
2. Create your feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add some amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## Acknowledgments

- [ClickHouse](https://clickhouse.com/) for the database
- [Spring Boot](https://spring.io/projects/spring-boot) for the backend framework
- [React](https://reactjs.org/) for the frontend library
- [Material-UI](https://mui.com/) for the UI components 