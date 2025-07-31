# Game Controller Pairing Guide

A comprehensive, responsive website that provides step-by-step instructions for powering on and pairing popular video game controllers. Built with HTML, CSS, and JavaScript, this website is designed to be deployed on GitHub Pages.

## 🎮 Controllers Covered

- **Xbox Series X Controller** - Microsoft's latest wireless controller
- **8BitDo SN30 Pro** - Versatile retro-style controller with modern connectivity

## 🎯 Supported Platforms

- **Xbox Series X/S** - Native support for Xbox controllers
- **Windows PC** - Bluetooth and USB connectivity
- **Steam Deck** - Full controller support with detailed pairing instructions
- **Nintendo Switch** - Compatible with 8BitDo controllers
- **Android Devices** - Mobile gaming support
- **macOS** - Apple computer compatibility

## ✨ Features

- **Responsive Design** - Works perfectly on desktop, tablet, and mobile devices
- **Interactive Modals** - Detailed step-by-step guides for each controller
- **Modern UI** - Beautiful gradient backgrounds and smooth animations
- **Accessibility** - Keyboard navigation and screen reader friendly
- **Cross-Platform Support** - Instructions for all major gaming platforms
- **Steam Deck Optimized** - Specialized instructions for Steam Deck users

## 🚀 Deployment to GitHub Pages

### Method 1: Direct Upload (Recommended for beginners)

1. **Create a new repository on GitHub**
   - Go to [GitHub](https://github.com) and click "New repository"
   - Name it `controller-pairing-guide` (or any name you prefer)
   - Make it public
   - Don't initialize with README (we'll upload our files)

2. **Upload the website files**
   - In your new repository, click "uploading an existing file"
   - Drag and drop all the files from this folder:
     - `index.html`
     - `styles.css`
     - `script.js`
     - `README.md`
     - `.github/workflows/` folder (for GitHub Actions)

3. **Enable GitHub Pages**
   - Go to your repository's **Settings** tab
   - Scroll down to the **Pages** section
   - Under "Source", select **Deploy from a branch**
   - Choose the **main** branch and **/(root)** folder
   - Click **Save**

4. **Your website is live!**
   - GitHub will provide you with a URL like: `https://yourusername.github.io/controller-pairing-guide`
   - It may take a few minutes to become available

### Method 2: Using Git (For developers)

1. **Initialize Git repository**
   ```bash
   git init
   git add .
   git commit -m "Initial commit"
   ```

2. **Connect to GitHub**
   ```bash
   git remote add origin https://github.com/yourusername/controller-pairing-guide.git
   git branch -M main
   git push -u origin main
   ```

3. **Enable GitHub Pages** (same as Method 1, steps 3-4)

## 🔧 GitHub Actions Setup

The repository includes GitHub Actions workflows for automatic deployment:

### Automatic Deployment Workflow
- **File**: `.github/workflows/static.yml`
- **Trigger**: Pushes to main branch
- **Action**: Automatically deploys to GitHub Pages

### How to Use GitHub Actions

1. **Upload the workflow files** along with your website files
2. **Push to main branch** - GitHub Actions will automatically run
3. **Monitor deployment** in the Actions tab of your repository
4. **Your site updates automatically** when you push changes

### Manual Deployment
You can also trigger deployments manually:
- Go to **Actions** tab in your repository
- Select the workflow
- Click **"Run workflow"**

## 📁 File Structure

```
controller-guide-website/
├── index.html                    # Main HTML file
├── styles.css                    # CSS styling
├── script.js                     # JavaScript functionality
├── README.md                     # This file
└── .github/
    └── workflows/
        ├── deploy.yml            # Full deployment workflow
        └── static.yml            # Simplified static site workflow
```

## 🎨 Customization

### Adding New Controllers

1. **Add a new controller card** in `index.html`:
   ```html
   <div class="controller-card" id="new-controller">
       <div class="controller-image">
           <i class="fas fa-gamepad"></i>
       </div>
       <h3>New Controller Name</h3>
       <p>Description of the controller</p>
       <button class="btn btn-primary" onclick="showGuide('new-controller')">
           View Guide
       </button>
   </div>
   ```

2. **Create a new modal** for the guide:
   ```html
   <div id="new-controller-modal" class="modal">
       <div class="modal-content">
           <div class="modal-header">
               <h2>New Controller Guide</h2>
               <span class="close" onclick="closeModal('new-controller-modal')">&times;</span>
           </div>
           <div class="modal-body">
               <!-- Add your guide content here -->
           </div>
       </div>
   </div>
   ```

3. **Update JavaScript** in `script.js`:
   ```javascript
   function showGuide(controllerType) {
       let modalId;
       
       if (controllerType === 'xbox-series-x') {
           modalId = 'xbox-modal';
       } else if (controllerType === '8bitdo-sn30pro') {
           modalId = '8bitdo-modal';
       } else if (controllerType === 'new-controller') {
           modalId = 'new-controller-modal';
       }
       
       if (modalId) {
           const modal = document.getElementById(modalId);
           modal.style.display = 'block';
           document.body.style.overflow = 'hidden';
       }
   }
   ```

### Adding Steam Deck Support

To add Steam Deck support for a new controller:

1. **Add a new guide section** in the modal:
   ```html
   <div class="guide-section">
       <h3><i class="fab fa-steam"></i> Pairing to Steam Deck</h3>
       <ol>
           <li>On your Steam Deck, go to <strong>Settings</strong> → <strong>Bluetooth</strong></li>
           <li>Make sure Bluetooth is turned <strong>ON</strong></li>
           <li>[Your specific pairing steps here]</li>
       </ol>
       <div class="note">
           <strong>Note:</strong> [Any important notes about Steam Deck compatibility]
       </div>
   </div>
   ```

### Changing Colors

The website uses CSS custom properties for easy color customization. In `styles.css`, you can modify:

- **Primary gradient**: `background: linear-gradient(135deg, #667eea 0%, #764ba2 100%)`
- **Xbox green**: `.xbox-icon { color: #107c10; }`
- **Retro purple**: `.retro-icon { color: #8b5cf6; }`
- **Steam dark**: `.fab.fa-steam { color: #171a21; }`

## 🔧 Technical Details

- **No build process required** - Pure HTML, CSS, and JavaScript
- **No dependencies** - Uses CDN for Font Awesome icons and Google Fonts
- **Mobile-first responsive design**
- **Progressive enhancement** - Works without JavaScript (basic functionality)
- **Accessibility compliant** - WCAG 2.1 AA standards
- **GitHub Actions ready** - Automatic deployment workflows included

## 📱 Browser Support

- Chrome 60+
- Firefox 55+
- Safari 12+
- Edge 79+
- Mobile browsers (iOS Safari, Chrome Mobile)

## 🎮 Steam Deck Specific Features

- **Native controller support** - Xbox Series X controller works out of the box
- **Mode-specific instructions** - 8BitDo SN30 Pro X-Input mode for best compatibility
- **Troubleshooting tips** - Steam Deck specific solutions
- **Firmware considerations** - Notes about Steam Deck updates

## 🤝 Contributing

Feel free to contribute by:
- Adding more controllers
- Improving the design
- Fixing bugs
- Adding new features
- Expanding Steam Deck support

## 📄 License

This project is open source and available under the [MIT License](LICENSE).

## 🆘 Troubleshooting

### Website not loading on GitHub Pages
- Check that all files are in the root directory of your repository
- Ensure the repository is public
- Wait 5-10 minutes for GitHub Pages to build and deploy

### GitHub Actions not working
- Verify the workflow files are in `.github/workflows/` directory
- Check the Actions tab for error messages
- Ensure the repository has proper permissions

### Modal not working
- Check browser console for JavaScript errors
- Ensure `script.js` is properly linked in `index.html`
- Verify that modal IDs match between HTML and JavaScript

### Styling issues
- Clear browser cache
- Check that `styles.css` is properly linked
- Verify CSS syntax is valid

### Steam Deck pairing issues
- Ensure Bluetooth is enabled on Steam Deck
- Try restarting the Steam Deck
- Update Steam Deck firmware if needed
- Use correct controller mode (X-Input for 8BitDo)

## 📞 Support

If you encounter any issues or have questions, please:
1. Check the troubleshooting section above
2. Search existing GitHub issues
3. Create a new issue with detailed information about your problem

---

**Happy gaming! 🎮** 