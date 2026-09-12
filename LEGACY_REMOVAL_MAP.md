# NYX - Legacy Removal Map

The following cancelled architecture related to the 3D orb and WebGL concepts has been completely removed from the repository.

## ORB SYSTEM
- `src/components/scene/Orb.tsx`
- `src/components/scene/OrbCanvas.tsx`
- `src/components/scene/FireMaterial.ts`
- `src/components/scene/CameraRig.tsx`

## PODIUM SYSTEM
- `src/components/scene/Podium.tsx`

## AUDIO
- `src/hooks/useFireAudio.ts` (Removed Web Audio API procedural fire audio)

## STATE
- `src/store/sceneStore.ts` (Removed Zustand store managing `scrollProgress`, `activeStage`, `orbTarget`, `dprTier`)

## UI INTEGRATION
- Removed `orb-canvas-container` styling from `src/index.css`
- Removed flame-related CSS variables (`--color-nyx-flame-*`) from `src/index.css`
- Removed orb target anchors and hover states from `src/components/sections/Showcase.tsx`
- Removed GSAP scroll sync related to `useSceneStore` from `src/App.tsx`
- Removed `OrbCanvas` and `useFireAudio` from `src/App.tsx`

## DEPENDENCIES
- `three`
- `@react-three/fiber`
- `@react-three/drei`
- `@types/three`
- `zustand` (Removed as it was solely used for the scene store)
