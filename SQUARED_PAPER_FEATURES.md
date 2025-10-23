# Squared Paper Grid - Feature Roadmap

## ✅ Essential Features (Implemented)
1. **Grid Enable/Disable** - Toggle grid on/off
2. **Grid Size** - Adjustable cell spacing (5-100px)
3. **Grid Color** - Customizable color for grid lines
4. **Real-time Pan/Zoom** - Grid moves with canvas transformations
5. **Proper Z-ordering** - Grid renders behind all elements (shapes, images, text)

## 📋 Nice-to-Have Features (Future)

### Visual Enhancements
6. **Grid Opacity** - Separate opacity control (0-100%) for subtlety
7. **Grid Style Options**:
   - Dots instead of lines
   - Dashed lines
   - Major/minor grid divisions (bold line every N squares)
8. **Dynamic Grid Scale** - Make grid spacing zoom-responsive (always visible at any zoom level)

### Functional Enhancements
9. **Snap to Grid** - Elements snap to grid intersections when moving/resizing
10. **Grid Origin Offset** - Allow offsetting grid origin (currently centered at 0,0)
11. **Per-Document Settings** - Save grid settings with the drawing file (persist in .excalidraw file)

### Advanced Grid Types
12. **Multiple Grid Types**:
    - Square grid (current default)
    - Isometric grid (for technical/architectural drawings)
    - Dot grid (for bullet journaling aesthetic)
    - Hex grid (for game maps and board layouts)

### Professional Features
13. **Ruler Mode** - Show measurements/units along canvas edges
14. **Guide Lines** - Draggable horizontal/vertical guides like in design tools (Figma, Sketch)
15. **Grid Export Options** - Choose to include/exclude grid in PNG/SVG exports
16. **Grid Presets** - Save and load custom grid configurations

## 🔧 Implementation Notes

### Current Implementation
The grid feature now uses **Excalidraw's built-in grid system**, which provides:
- Native rendering on the StaticCanvas layer
- Automatic pan/zoom synchronization
- Proper layering (behind all elements)
- Performance optimization built into Excalidraw

### AppState Properties Used
```typescript
{
  gridModeEnabled: boolean,     // Toggle grid
  gridSize: number,             // Cell size in pixels
  gridStep: number,             // Major grid line step multiplier
  gridColor: {                  // Grid colors
    Bold: string,               // Major grid lines
    Regular: string             // Regular grid lines
  },
  gridDirection: {              // Direction toggles
    horizontal: boolean,
    vertical: boolean
  }
}
```

### Plugin Settings Mapping
- `squaredPaperEnabled` → `gridModeEnabled`
- `squaredPaperSize` → `gridSize`
- `squaredPaperColor` → `gridColor.Regular` and `gridColor.Bold`

## 📝 Development Priority

**Phase 1: Core Grid (✅ Complete)**
- Essential features 1-5

**Phase 2: Visual Polish (Future)**
- Features 6-8
- Estimated effort: 1-2 days

**Phase 3: Functional Enhancements (Future)**
- Features 9-11
- Estimated effort: 2-3 days

**Phase 4: Advanced Features (Future)**
- Features 12-16
- Estimated effort: 5-7 days

## 🐛 Known Issues
None - the built-in grid system works perfectly!

## 💡 User Feedback
_(Track user-reported issues and feature requests here)_

---

**Last Updated**: 2025-10-23
**Plugin Version**: 2.2.5
**Excalidraw Version**: 0.18.0-41
