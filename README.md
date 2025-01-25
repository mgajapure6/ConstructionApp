# ConstructionApp

Database schema for construction app

CREATE TABLE Project (
    ProjectID INT PRIMARY KEY AUTO_INCREMENT,
    ProjectName VARCHAR(255) NOT NULL,
    Description TEXT,
    StartDate DATE NOT NULL,
    ExpectedEndDate DATE,
    ActualEndDate DATE,
    Location VARCHAR(255),
    ClientID INT,
    ContractorID INT,
    ProjectManager VARCHAR(100),
    Budget DECIMAL(15, 2),
    CurrentSpend DECIMAL(15, 2),
    Status VARCHAR(50),
    Phase VARCHAR(50),
    Permits TEXT,
    RiskLevel VARCHAR(20),
    Notes TEXT,
    LastUpdated TIMESTAMP DEFAULT CURRENT_TIMESTAMP ON UPDATE CURRENT_TIMESTAMP,
    Attachments TEXT,
    SubcontractorID INT,
    MaterialCost DECIMAL(15, 2),
    LaborCost DECIMAL(15, 2),
    EquipmentCost DECIMAL(15, 2),
    OverheadCost DECIMAL(15, 2),
    ContingencyBudget DECIMAL(15, 2),
    ChangeOrders INT,
    Milestones TEXT,
    QualityControlCheckpoints TEXT,
    SafetyIncidents INT,
    EnvironmentalImpact TEXT,
    RegulatoryCompliance TEXT,
    WarrantyPeriod INT,
    CloseoutDate DATE,
    Feedback TEXT,
    LessonsLearned TEXT,
    Revisions INT,
    PaymentStatus VARCHAR(50),
    InvoiceNumbers TEXT,
    InsuranceDetails TEXT,
    ProjectType VARCHAR(100),
    SizeSqFt DECIMAL(10, 2),
    CompletionPercentage DECIMAL(5, 2),
    ScheduledDowntime TEXT
);

-- Assuming there might be foreign key relationships, you could add these after table creation:
ALTER TABLE ConstructionProjects
ADD FOREIGN KEY (ClientID) REFERENCES Clients(ClientID),
ADD FOREIGN KEY (ContractorID) REFERENCES Contractors(ContractorID),
ADD FOREIGN KEY (SubcontractorID) REFERENCES Subcontractors(SubcontractorID);



CREATE TABLE Clients (
    ClientID INT PRIMARY KEY AUTO_INCREMENT,
    ClientName VARCHAR(255) NOT NULL,
    ContactName VARCHAR(100),
    Email VARCHAR(255) UNIQUE,
    Phone VARCHAR(20),
    Address TEXT,
    City VARCHAR(100),
    State VARCHAR(100),
    Country VARCHAR(100),
    PostalCode VARCHAR(20),
    CompanyType VARCHAR(50),
    Industry VARCHAR(100),
    Notes TEXT,
    CreatedAt TIMESTAMP DEFAULT CURRENT_TIMESTAMP,
    UpdatedAt TIMESTAMP DEFAULT CURRENT_TIMESTAMP ON UPDATE CURRENT_TIMESTAMP
);
