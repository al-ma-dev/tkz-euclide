# Changelog — tkz-euclide

All notable changes to this project will be documented here.
The version suffix **c** indicates the CTAN release.
Format based on [Keep a Changelog](https://keepachangelog.com/en/1.1.0/).
---
## [5.15c] — 2026/11/26
### Fixed
- `\tkzInterLC` with a line through the centre of the circle: the order of the two points depended on rounding (the luaLaTeX and TeX versions could give them in opposite order). The second point is now always in the direction of the line, from its first point to its second point.
- Documentation: FAQ (`\tkzDefCircle[R]` instead of the removed `\tkzDrawCircle[R]`) and default option of `\tkzDefCircle` (`R`).

## [5.14c] — 2026/10/16
### Fixed
- `\tkzDefCircle[orthogonal from=…]` / `[orthogonal through=…]`: the choice leaked globally; every later `\tkzDefCircle(A,B,C)` without option failed.
- `\tkzShowLine`: options were global (`parallel`, `orthogonal`, `bisector` stayed active in the following pictures); the mediator is again the default at each call.
- `\tkzDefSimilitudeCenter`: `int`/`ext` stayed active for the following calls.
- `\tkzIsLinear` always answered true; `\tkzIsLinear` and `\tkzIsOrtho` now use a tolerance relative to the lengths (0.06°).
- `\tkzPowerCircle`: the result is frozen (it changed after another calculation).
- `\tkzCalcLength`: `cm=false` no longer persists to the following calls.
- `\tkzDefCircleBy[inversion=…]`: a circle passing near (less than 1 cm) the centre of inversion was transformed into a line.
- `\tkzDefCircle[spieker]`: `\tkzGetLength` gives the radius in cm like the other circles.
- `\tkzDefTriangleCenter[feuerbach]` sometimes returned the wrong point; `\tkzDefSpcTriangle[feuerbach]` now uses the line nine-point centre–excenter (exact tangency points).
- `\tkzDrawPolySeg`: no more zero-length first segment (wrong start arrow with `<->`).
- `\tkzCompass` accepts a decimal `delta`.
- `\tkzProtractor[return]` had no effect.
- `\tkzLabelRegPolygon` uses its `sep` option; `\tkzDrawX` uses its `step` option like `\tkzDrawY`.
- `\tkzDrawCircle` / `\tkzFillCircle` with three points (v3 syntax) gave an endless loop; a clear error is now given.
- Options of `\tkzGrid`, `\tkzClip`, `\tkzDefEquiPoints` and `\tkzLegend` are local to the call.
- Aliases `\tkzDefNinePointsCircle`, `\tkzFeuerBachCircle` and `\tkzIncentralTriangle` pointed to undefined macros.
- `tkz-euclide.sty`: `\RequirePackage{xpatch}`, warning instead of an undefined `\PatchFailed`, dead second `\ProcessOptions` removed.

### Changed
- `\tkzSetUpCompass[delta=…]` only acts on compass marks; arcs (`\tkzDrawArc`, `\tkzMarkArc`, `\tkzLabelArc`) are set with `\tkzSetUpArc[delta=…]`.
- The TikZ style `help lines` is no longer redefined for the whole document; `\tkzHelpGrid` is unchanged.

---
## [5.13c] — 2026/01/25
### Fixed
   - Harmonization of file dates.
   - Simplification and correction of file headers.
   - Creating a repository on GitHub.
   - Added a warning for using the **mini** option in conjunction with **tkz-elements**:

   Some macros, such as those in the `tkz-draw-eu-show.tex` file, still require the use of the complete package.

---
## [5.12c] — 2026/01/22
### Fixed
- Macro `\tkzAutoLabelPoints`.
- Modification of files loaded with the `mini` option. If you encounter difficulties, do not use this option because some macros require the use of macros for calculations.

### Docs
- Correction  Example with `\tkzAutoLabelPoints`.


---

## [5.11c] — 2025/09/17
### Fixed
- Macro `\tkzClipSector`.

### Docs
- Example *Pentagon in a square*.
- Example *Part I: golden triangle* in the **Presentation** section.

---

## [5.10c]
### Added
- `mini` option.
- French documentation on [altermundus.fr](http://altermundus.fr).

### Changed
- Extracted `tkz-tool-eu-angles.arc.tex` from `tkz-tool-eu-angles.tex`.

---

## [5.06c]
### Added
- `\tkzSetUpCircle`.

### Fixed
- Bug in `\tkzLabelAngle` with option `angle`.
- Typos in the documentation.

### Removed
- Obsolete French texts.

---

## [5.05c]
### Fixed
- Documentation corrections.

---

## [5.04c]
### Changed
- Renamed several files.

---

## [5.03c]
### Added
- Macro `\tkzDrawEllipse`.

### Fixed
- Bug in `tkz-obj-lua-points-spc.tex` (`\tkzDefBarycentricPointTwo`).

---

## [5.02c]
### Fixed
- Duplicate macro in `tkz-lib-eu-shape.tex`.
- Removed duplicate definitions in `tkz-draw-eu-points.tex`.

---

## [5.01c]
### Added
- File `tkz-obj-eu-points-spc.tex`.

### Changed
- Cleaned `tkz-tools-lua-math.tex`.

### Fixed
- Incorrect date in `tkz-euclide.sty`.

---

## [5.00c]
### Added
- **`lua` option** for performing calculations with Lua (faster and more precise).

---

## [4.25c]
### Removed
- `\input{tkz-obj-eu-draw-triangles.tex}` from the list of loaded files.

---

## [4.24c]
### Changed
- Macro `\tkzDefCircle[apollonius]`.

### Fixed
- Bug in `\tkzMarkAngle`.

---

## [4.23c]
### Changed
- Macro `\tkzDefRadicalAxis`.

### Fixed
- Bug in `\tkzDrawSemiCircle`.

### Removed
- Deprecated code.

---

## [4.22c]
### Changed
- Documentation updated (clarified usage of `\tkzDefCircle[R](...)`).

### Fixed
- Bug in `\tkzMarkAngle`.

### Removed
- Obsolete options for `\tkzDrawCircle` (now always requires center + one point).

---

## [4.21c]
### Fixed
- Corrupted archive (all `|` symbols disappeared).

---

## [4.20c ... 4.00c] — Major restructuring
### Added
- `\tkzDefLine[euler]`, `\tkzDefLine[altitude]`, `\tkzDefLine[tangent ...]`.
- `\tkzPicAngle`, `\tkzFillAngles`.
- `\tkzDotProduct`, `\tkzPowerCircle`, `\tkzDefRadicalAxis`.
- `\tkzIsOrtho`, `\tkzIsLinear`.
- Arc options: `reverse`, `next to`, `in rad`.
- Vector style: `\tikzset{vector style/.style={>=Latex,->}}`.
- Arrow options for lines and circles.

### Changed
- Unified label styles (only `label style` remains).
- Circle inversion rewritten.
- Argument order of `\tkzDefPointOnCircle` modified.
- Documentation extensively revised.

### Removed
- Deprecated macros: `\tkzDrawTriangle`, `\tkzDrawSquare`, `\tkzDrawGoldRectangle`, etc.
- Old options (`label seg style`, `label line style`, `label angle style`).
