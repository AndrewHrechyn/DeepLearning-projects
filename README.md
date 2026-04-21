# Deep Learning Projects 🤖

Collection of deep learning projects focused on computer vision and neural networks.

## 📁 Repository Structure

```
DeepLearning-projects/
├── people_counter/
│   ├── docs/
│   │   ├── info.md                    # Detailed documentation about CSRNet
│   │   ├── 1802.10062v4.pdf          # Research paper (CSRNet original)
│   │   └── 2106.04400v2.pdf          # Related research paper
│   └── src/
│       └── people-counter.ipynb       # Main implementation & training notebook
│
├── .gitignore
├── README.md
```

## 🎯 Projects Overview

### 1. People Counter - CSRNet Implementation

**Objective**: Implement and train CSRNet (Congestion Scene Recognition Network) for counting people in dense crowds.

#### 📖 What is CSRNet?

CSRNet is a deep learning architecture designed specifically for counting objects (primarily people) in crowded scenes. Rather than detecting individual people with bounding boxes (which fails in very dense crowds), CSRNet generates a **density map** that represents the distribution of people across the image.

**Key Features:**
- **Architecture**: Combines VGG-16 frontend with dilated convolutions backend
- **Output**: Density map where pixel intensity correlates with crowd density
- **Application**: Crowd counting, cell counting, wildlife monitoring, traffic analysis

#### 🏗️ Model Architecture

| Component | Purpose |
|-----------|---------|
| **Frontend** | VGG-16 (first 10 layers) - Feature extraction |
| **Backend** | Dilated Convolutions - Context-aware density estimation |

#### ⚙️ How It Works

1. Input: Image of a crowd
2. Frontend extracts visual features (edges, textures, shapes)
3. Backend generates a density map (heatmap)
4. Total count = Sum of all values in the density map

#### ✅ Advantages

✓ Handles variable crowd densities (sparse to extremely dense)  
✓ Preserves spatial information through dilated convolutions  
✓ Efficient on GPU hardware  
✓ Proven baseline for crowd counting tasks  
✓ Relatively simple to implement and debug in PyTorch

#### 📊 Performance & Relevance (2026)

- **Baseline Model**: Still used as a reference point for new architectures
- **Dataset Performance**: Trained on ShanghaiTech and UCF_CC_50 datasets
- **Real-time capable**: Suitable for GPU inference on moderate hardware
- **Production-ready**: Stable and well-documented implementation

#### 🔬 Related Research

- Primary paper: arXiv:1802.10062v4 (included in docs/)
- Supporting paper: arXiv:2106.04400v2 (included in docs/)
- See `people_counter/docs/info.md` for detailed technical overview

#### 🚀 Use Cases

- 🏙️ Smart city crowd monitoring
- 🔬 Microscopy cell counting
- 🛸 Wildlife population monitoring (drone-based)
- 🚗 Traffic flow analysis
- 📊 Event capacity management

## 🛠️ Tech Stack

- **Language**: Python 3.x
- **Deep Learning**: PyTorch
- **Notebook**: Jupyter
- **Visualization**: Matplotlib, OpenCV
- **Scientific**: NumPy, SciPy

## 📝 Getting Started

1. **Clone repository**
   ```bash
   git clone https://github.com/AndrewHrechyn/DeepLearning-projects.git
   cd DeepLearning-projects
   ```

2. **Install dependencies**
   ```bash
   pip install torch torchvision jupyter matplotlib opencv-python numpy scipy
   ```

3. **Run the notebook**
   ```bash
   jupyter notebook people_counter/src/people-counter.ipynb
   ```

4. **Read documentation**
   - Start with `people_counter/docs/info.md` for overview
   - Check research papers in `people_counter/docs/` for technical details

## 📚 References & Resources

- **CSRNet Paper**: Li et al., "CSRNet: Dilated Convolutions for Mobile Crowd Counting" (2018)
- **Related Work**: Included research papers in docs folder
- **Datasets**: ShanghaiTech, UCF_CC_50
- **Implementation**: PyTorch-based, fully reproducible

## 👤 Author

**Andrew Hrechyn** - [@AndrewHrechyn](https://github.com/AndrewHrechyn)

## 📄 License

This project is open source and available under the MIT License (or specify your preferred license).

## 🔗 Additional Notes

- For SOTA (State-of-the-Art) models, see discussion in `people_counter/docs/info.md`
- CSRNet serves as excellent baseline for custom crowd counting solutions
- Suitable for educational purposes and production deployment
