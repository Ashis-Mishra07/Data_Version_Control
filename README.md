# Data Version Control (DVC)

## Overview
DVC (Data Version Control) is an open-source tool designed to manage machine learning projects efficiently. 
It provides versioning for data and models, facilitates reproducibility, and integrates seamlessly with Git.

DVC is particularly useful when dealing with large datasets that cannot be stored directly in a Git repository due to size limitations. 
Instead of keeping the data within Git, DVC enables users to track and manage datasets stored on external cloud services or remote servers.
This allows teams to collaborate effectively without needing to download massive files, improving efficiency and workflow.

Similar to how counters in C++ provide unique identifiers, DVC generates a unique hash key for each data item. 
This hash key acts as an identifier, ensuring proper versioning and tracking without duplicating data. 
By leveraging these hash-based references, DVC enables efficient storage and retrieval of datasets across different environments.

## Features
- **Data Versioning**: Track large datasets and machine learning models just like code.
- **Pipeline Management**: Define ML pipelines using `dvc.yaml` for easy reproducibility.
- **Storage Agnostic**: Supports remote storage options such as S3, Google Drive, Azure Blob, etc.
- **Collaboration**: Share datasets and model checkpoints efficiently across teams.
- **Efficiency**: Avoid redundant data duplication using a content-addressable storage mechanism.

## Installation
To install DVC, use:
```sh
pip install dvc
```
For specific storage support, install the appropriate version:
```sh
pip install dvc[s3]
```

## Getting Started
### Initialize DVC
```sh
git init
dvc init
```

### Track a Dataset
```sh
dvc add data.csv
git add data.csv.dvc .gitignore
git commit -m "Track dataset with DVC"
```

### To be Added in dvc file 
```sh
dvc.txt
```

### To be Added in git file
```sh
dvc.txt.dvc
.gitignore  (inside dvc file)
```

### To Checkout
```sh
git checkout hash_key
dvc ckeckout


# To get into updated
git checkout master   ( master form git branch )
dvc checkout

```

## Best Practices
- Use `.dvcignore` to exclude unnecessary files from tracking.
- Regularly push data to remote storage to ensure team accessibility.
- Automate DVC commands in CI/CD pipelines for efficient workflow.

## Resources
- [DVC Documentation](https://dvc.org/doc)
- [DVC GitHub Repository](https://github.com/iterative/dvc)

## License
This project is licensed under the MIT License.
