# Resume with PDF Download

A modern, responsive resume website with ATS-optimized PDF download functionality.

## Features

- **Responsive Design**: Looks great on all devices
- **Print Optimization**: Carefully crafted print styles for professional appearance
- **ATS-Optimized PDF**: Generated PDFs are optimized for Applicant Tracking Systems
- **One-Click Download**: Download button generates and downloads PDF instantly
- **Live Development**: Hot-reload development environment with Gulp

## Quick Start

### Prerequisites

- Node.js (v14 or higher)
- npm

### Installation

1. Clone or download this repository
2. Install dependencies:
   ```bash
   npm install
   ```

### Development

#### Standard Development (without PDF functionality)

```bash
npm start
```

This starts the Gulp development server at `http://localhost:3000`

#### Development with PDF Download

```bash
npm run start:pdf
```

This starts both:

- Gulp development server at `http://localhost:3000`
- PDF generation server at `http://localhost:3001`

The resume will be available at `http://localhost:3000` with a working "Download PDF" button.

### PDF Generation

The PDF download functionality includes:

- **ATS Optimization**: Text is selectable and searchable
- **Professional Formatting**: Clean, readable layout
- **Proper Typography**: Uses standard fonts (Arial/Helvetica)
- **Structured Content**: Proper heading hierarchy for ATS parsing
- **Print-Optimized**: Fits perfectly on standard letter-size paper

## Project Structure

```
├── src/
│   ├── index.pug              # Main template
│   ├── assets/
│   │   ├── data/              # YAML data files
│   │   ├── style/             # SCSS stylesheets
│   │   │   ├── _print.scss    # Print/PDF optimizations
│   │   │   └── ...
│   │   ├── js/                # JavaScript files
│   │   │   └── pdf-download.js # PDF download functionality
│   │   └── img/               # Images
├── dist/                      # Built files (generated)
├── pdf-server.js              # PDF generation server
├── start-with-pdf.js          # Development startup script
└── gulpfile.js                # Build configuration
```

## Customization

### Content

Edit the YAML files in `src/assets/data/` to update your resume content:

- `contact-info.yml` - Personal information
- `work-history.yml` - Work experience
- `skills.yml` - Skills and competencies
- `education.yml` - Education details
- `references.yml` - References

### Styling

- `src/assets/style/_layout.scss` - Layout and responsive design
- `src/assets/style/_typography.scss` - Fonts and text styling
- `src/assets/style/_print.scss` - Print and PDF optimizations

### Print Optimization

The resume uses utility classes for print optimization:

- `.no-print` - Hide from print/PDF
- `.print-only` - Show only in print/PDF
- `.print-hide` - Hide from print (show on screen)

See `PRINT-OPTIMIZATION.md` for detailed documentation.

## PDF Optimization Features

### ATS Compatibility

- **Selectable Text**: All text is selectable and searchable
- **Standard Fonts**: Uses Arial/Helvetica for maximum compatibility
- **Proper Structure**: Semantic HTML with proper heading hierarchy
- **Clean Formatting**: No decorative elements that confuse ATS
- **High Contrast**: Black text on white background

### Human Readability

- **Professional Layout**: Clean, organized appearance
- **Proper Spacing**: Optimized margins and line heights
- **Readable Typography**: Appropriate font sizes and weights
- **Logical Flow**: Information presented in logical order

## Scripts

- `npm start` - Start development server (Gulp only)
- `npm run start:pdf` - Start development with PDF functionality
- `npm run pdf-server` - Start PDF server only

## Technical Details

### PDF Generation

The PDF is generated using Puppeteer, which:

1. Launches a headless Chrome browser
2. Navigates to the resume page
3. Applies print styles automatically
4. Generates a high-quality PDF
5. Serves it for download

### Browser Compatibility

- Chrome/Chromium (recommended)
- Firefox
- Safari
- Edge

### Dependencies

- **Gulp**: Build system and development server
- **Pug**: Template engine
- **Sass**: CSS preprocessing
- **Puppeteer**: PDF generation
- **Express**: PDF server
- **Browser-Sync**: Live reload

## Troubleshooting

### PDF Download Not Working

1. Make sure you're using `npm run start:pdf` (not just `npm start`)
2. Check that both servers are running (Gulp at :3000, PDF at :3001)
3. Ensure Puppeteer installed correctly: `npm install puppeteer`

### Build Issues

1. Clear node_modules and reinstall: `rm -rf node_modules && npm install`
2. Make sure you have Node.js v14 or higher
3. Check for any missing dependencies

### Print Styles Not Applied

1. Use browser's print preview to test print styles
2. Check that `_print.scss` is being imported in `main.scss`
3. Ensure print media queries are not being overridden

## License

This project is open source and available under the ISC License.
