### **Conda Commands Cheat Sheet**

#### **1. Create a Conda Environment**
```sh
conda env create -f References/environment.yml
```

#### **2. Activate an Environment**
```sh
conda activate env_name
```

#### **3. List All Environments**
```sh
conda env list
```

#### **4. Remove an Environment (If Needed)**
```sh
# First, deactivate if it's active
conda deactivate

# Then, remove the environment
conda env remove -n env_name
```

#### **5. Check Installed Packages in an Environment**
```sh
conda list
```

#### **6. Check Dependencies of a Specific Package**
```sh
conda search package_name --info
```

#### **7. Install a New Package**
- **Using Conda:**  
  ```sh
  conda install package_name
  ```
- **Using Pip inside the Conda environment:**  
  ```sh
  pip install package_name
  ```
- **Using UV (for faster installs with better dependency resolution):**  
  ```sh
  uv pip install package_name
  ```

#### **8. Update All Packages in an Environment**
```sh
conda update --all
```

#### **9. Remove a Specific Package from an Environment**
```sh
conda remove package_name
```

#### **10. Clean Conda Cache (If Needed)**
```sh
conda clean --all
```

#### **11. Export Environment (After Adding New Packages)**
```sh
conda env export > References/environment.yml
```

#### **12. Update Dependencies After Modifying `environment.yml`**
```sh
conda env update -f References/environment.yml --prune
```