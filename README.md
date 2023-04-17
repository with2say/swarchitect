# swarchitect


graph TB;

    subgraph Explain
        NumericalModelExplainer
        ImageModelExplainer
    end

    subgraph Analysis
        KnownFeatureAnalysis
        UnknownFeatureAnalysis
        PhysicalFailureAnalysis
        RiskPatternPrediction
    end

    subgraph Model
        ModelInterface
        NumericalModel
        ImageModel
    end

    subgraph Data
        DataModule
        DataExtractor
    end

    NumericalModelExplainer --> KnownFeatureAnalysis
    ImageModelExplainer --> UnknownFeatureAnalysis
    ImageModelExplainer --> PhysicalFailureAnalysis 
    ImageModelExplainer --> RiskPatternPrediction

    KnownFeatureAnalysis -->|depends on| ModelInterface
    UnknownFeatureAnalysis -->|depends on| ModelInterface
    PhysicalFailureAnalysis -->|depends on| ModelInterface
    RiskPatternPrediction -->|depends on| ModelInterface

    ModelInterface -->|depends on| DataModule;

    DataModule --> |depends on| DataExtractor;


