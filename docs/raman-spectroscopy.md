# Raman Spectroscopy

The schema below provides a human-readable documentation about properties of the given analytical method. The current version is situated in a [google document](https://docs.google.com/spreadsheets/d/1kvKDOLsvT4hhcDzLs0DATZsnq2TAGUlYFTWcoL8tOHg/edit?gid=1535944120#gid=1535944120) and we welcome any feedback to improve its usability. 

The schema parameters are referenced from several sources published by [Crystallography Open Database](https://wiki.crystallography.net/cif/dictionaries/cif_raman_0.3.1/), [IRUG Spectral Database], [Raman Spectroscopy Terminology Guide](https://cdn.sanity.io/files/0vv8moc6/spectroscopy/ab7e46014be47cfaf9ebe9851d205da35cd269f1.pdf/Spectroscopy_February2020supp.pdf), and [technical specifications in journal articles]. 

In the future, we will offer other data formats, such as **JSON** and **RDF/XML** , as they may be required for electronic laboratory notebooks or a knowledge graph powered by the SPARQL query.  

## 1. Laser

*Amplified light used to genenrate Raman spectra*.

### 1.1 Wavelength

URI: <https://w3id.org/my-schema#PreferredLabel>
!!! note
    - **Preferred label:** waveLength
    - **Definition:** The wavelength of the excitation laser used in Raman analysis, typically measured in nanometers (nm). It determines the energy of the incident photons and influences both the Raman scattering efficiency and potential fluorescence.
    - **Data type:** integer
    - **Obligation:** mandatory
    - **Occurrences:** 1
    - **Allowed values:** free text
    - **Reference:**
    - **Comments:**
    - **Example:** 532nm

### 1.2 Laser Power

URI: <https://w3id.org/my-schema#PreferredLabel>
!!! note
    - **Preferred label:** laserPower
    - **Definition:** The laser power delivered at the sample surface, usually measured in milliwatts (mW). It affects signal intensity but also the risk of heating or damaging sensitive samples.
    - **Data type:** double
    - **Obligation:** mandatory
    - **Occurrences:** 1
    - **Allowed values:** free text
    - **Reference:**
    - **Comments:**
    - **Example:** 10mW

### 1.3 Spot Size

URI: <https://w3id.org/my-schema#PreferredLabel>
!!! note
    - **Preferred label:** spotSize
    - **Definition:** The diameter of the laser beam focused on the sample, typically in micrometers (µm). Smaller spot sizes allow for higher spatial resolution in micro-Raman analysis.
    - **Data type:** double
    - **Obligation:** recommended
    - **Occurrences:** 0–1
    - **Allowed values:** free text
    - **Reference:** [CIF_Raman:_raman_measurement_device.spot_size](https://wiki.crystallography.net/cif/dictionaries/cif_raman_0.3.1/#index41h3)
    - **Comments:**
    - **Example:** 1μm

### 1.4 Laser Source

URI: <https://w3id.org/my-schema#PreferredLabel>
!!! note
    - **Preferred label:** laserSource
    - **Definition:** The source of laser used for excitation in Raman spectroscopy, characterized by its wavelength, coherence, stability, and beam quality.
    - **Data type:** string
    - **Obligation:** optional
    - **Occurrences:** 0–1
    - **Allowed values:** controlled list `[argon-krypton, argon, krypton, helium-neno, xenon, nitrogen, excimer, helium-cadium, helium-mercury, helium-selenium, helium-silver, strontium-vapor, gold-vapor, manganese, ruby, titanium-sapphire,cerium, chromium, other]`
    - **Reference:** [CIF_Raman:_raman_measurement_device.excitation_laser_type](https://wiki.crystallography.net/cif/dictionaries/cif_raman_0.3.1/#index33h3)
    - **Comments:**
    - **Example:**  argon

### 1.5 Laser Defocus

URI: <https://w3id.org/my-schema#PreferredLabel>
!!! note
    - **Preferred label:** laserDefocus
    - **Definition:** An intentional adjustment of the laser’s focus above or below the sample surface to reduce power density, prevent damage, or average signal over a larger area
    - **Data type:** boolean
    - **Obligation:** optional
    - **Occurrences:** 0–1
    - **Allowed values:** controlled list
    - **Reference:**
    - **Comments:**
    - **Example:** Yes

## 2. Spectrometer

*The main component used to separate and measure the wavelengths of scattered light*.

### 2.1 Integration Time

URI: <https://w3id.org/my-schema#PreferredLabel>
!!! note
    - **Preferred label:** integrationTime
    - **Definition:** Duration over which the detector collects photons for a single scan, measured in seconds. Affects signal strength and noise. Also known as exposure time
    - **Data type:** double
    - **Obligation:** mandatory
    - **Occurrences:** 1
    - **Allowed values:** free text
    - **Reference:**
    - **Comments:**
    - **Example:** 10 s

### 2.2 Accumulation

URI: <https://w3id.org/my-schema#PreferredLabel>
!!! note
    - **Preferred label:** accumulation
    - **Definition:** Number of scans averaged together to improve signal-to-noise ratio
    - **Data type:** integer
    - **Obligation:** mandatory
    - **Occurrences:** 1
    - **Allowed values:** free text
    - **Reference:**
    - **Comments:**
    - **Example:** 10

### 2.3 Background Scan

URI: <https://w3id.org/my-schema#PreferredLabel>
!!! note
    - **Preferred label:** backgroundScan
    - **Definition:** A scan taken without the sample to measure background signal (e.g., system or substrate noise), later subtracted from the sample data. Measured in second.
    - **Data type:** double
    - **Obligation:** optional
    - **Occurrences:** 0–1
    - **Allowed values:** free text
    - **Reference:**
    - **Comments:**
    - **Example:** 2 s

### 2.4 Collection Time

URI: <https://w3id.org/my-schema#PreferredLabel>
!!! note
    - **Preferred label:** collectionTime
    - **Definition:** Total time used to acquire the spectrum, often: integration time × number of accumulations. Measured in second.
    - **Data type:** double
    - **Obligation:** optional
    - **Occurrences:** 0–1
    - **Allowed values:** free text
    - **Reference:**
    - **Comments:**
    - **Example:** 100 s

### 2.5 Photobleaching Time

URI: <https://w3id.org/my-schema#PreferredLabel>
!!! note
    - **Preferred label:** photobleachingTime
    - **Definition:** Duration over which photobleaching (loss of signal due to light-induced degradation) is observed or mitigated before acquisition. Measured in second. 
    - **Data type:** double
    - **Obligation:** optional
    - **Occurrences:** 0–1
    - **Allowed values:** free text
    - **Reference:**
    - **Comments:**
    - **Example:** 2 s

### 2.6 Resolution

URI: <https://w3id.org/my-schema#PreferredLabel>
!!! note
    - **Preferred label:** resolution
    - **Definition:** The ability of the spectrometer to distinguish between closely spaced Raman peaks, usually in cm⁻¹.
    - **Data type:** double
    - **Obligation:** mandatory
    - **Occurrences:** 1
    - **Allowed values:** free text
    - **Reference:**
    - **Comments:**
    - **Example:** 2 cm⁻¹

### 2.7 Cutoff Frequency

URI: <https://w3id.org/my-schema#PreferredLabel>
!!! note
    - **Preferred label:** cutoffFrequency
    - **Definition:** The lowest wavenumber from which Raman signals can be reliably measured; limited by filters or optics, usually in cm⁻¹. 
    - **Data type:** double
    - **Obligation:** optional
    - **Occurrences:** 0–1
    - **Allowed values:** free text
    - **Reference:**
    - **Comments:**
    - **Example:** 180 cm-1

### 2.8 Maximum Range

URI: <https://w3id.org/my-schema#PreferredLabel>
!!! note
    - **Preferred label:** maxRange
    - **Definition:** The maximum Raman shift (in cm⁻¹) detectable in a spectrum.
    - **Data type:** double
    - **Obligation:** mandatory
    - **Occurrences:** 1
    - **Allowed values:** free text
    - **Reference:**
    - **Comments:**
    - **Example:** 1850 cm⁻¹

### 2.9 Minimum Range

URI: <https://w3id.org/my-schema#PreferredLabel>
!!! note
    - **Preferred label:** minRange
    - **Definition:** The minimum Raman shift (in cm⁻¹) detectable in a spectrum.
    - **Data type:** double
    - **Obligation:** mandatory
    - **Occurrences:** 1
    - **Allowed values:** free text
    - **Reference:**
    - **Comments:**
    - **Example:** 50 cm⁻¹

### 2.10 Calibration

URI: <https://w3id.org/my-schema#PreferredLabel>
!!! note
    - **Preferred label:** calibration
    - **Definition:** Process of adjusting the spectrometer's wavelength axis to known reference peaks (e.g., silicon at 520.7 cm⁻¹).
    - **Data type:** array
    - **Obligation:** Recommended
    - **Occurrences:** 0–n
    - **Reference:**
    - **Comments:**

#### 2.10.1 Calibration Material

URI: <https://w3id.org/my-schema#PreferredLabel>
!!! note
    - **Preferred label:** calibrationMaterial
    - **Definition:** Standard used for calibration (e.g., silicon, diamond, polystyrene).
    - **Data type:** string
    - **Obligation:** mandatory
    - **Occurrences:** 1
    - **Allowed values:** controlled list
    - **Reference:**
    - **Comments:**
    - **Example:** silicon_wafer

#### 2.10.2 Calibration Position

URI: <https://w3id.org/my-schema#PreferredLabel>
!!! note
    - **Preferred label:** calibrationPosition
    - **Definition:** The peak position against which the standard material is calibrated in cm⁻¹. 
    - **Data type:** double
    - **Obligation:** mandatory
    - **Occurrences:** 1
    - **Allowed values:** free text 
    - **Reference:**
    - **Comments:**
    - **Example:** 520.7 cm⁻¹

### 2.11 Optical Filter

URI: <https://w3id.org/my-schema#PreferredLabel>
!!! note
    - **Preferred label:** opticalFilter
    - **Definition:** Filters (e.g., edge or notch) used to block Rayleigh scattering and allow only Raman-shifted light to reach the detector.
    - **Data type:** array
    - **Obligation:** recommended
    - **Occurrences:** 0–n
    - **Reference:**
    - **Comments:**

#### 2.11.1 Filter Type

URI: <https://w3id.org/my-schema#PreferredLabel>
!!! note
    - **Preferred label:** filterType
    - **Definition:** Type of filters. 
    - **Data type:** string
    - **Obligation:** mandatory
    - **Occurrences:** 1
    - **Allowed values:** controlled list
    - **Reference:**
    - **Comments:**
    - **Example:** edge

#### 2.11.2 Filter Specification

URI: <https://w3id.org/my-schema#PreferredLabel>
!!! note
    - **Preferred label:** filterSpecification
    - **Definition:** State the transmission percentage and optical density (OD) of the filter. 
    - **Data type:** string
    - **Obligation:** optional
    - **Occurrences:** 0–1
    - **Allowed values:** free text
    - **Reference:**
    - **Comments:**
    - **Example:** 25%(OD0.6)

### 2.12 Grating

URI: <https://w3id.org/my-schema#PreferredLabel>
!!! note
    - **Preferred label:** grating
    - **Definition:** The dispersive element that separates light by wavelength through diffraction.
    - **Data type:** array
    - **Obligation:** recommended
    - **Occurrences:** 0–n
    - **Reference:**
    - **Comments:**

#### 2.12.1 Grating Type

URI: <https://w3id.org/my-schema#PreferredLabel>
!!! note
    - **Preferred label:** gratingType
    - **Definition:** Specifies whether the grating is ruled, holographic, or echelle, affecting resolution and stray light
    - **Data type:** string
    - **Obligation:** recommended
    - **Occurrences:** 0–1
    - **Allowed values:** controlled list
    - **Reference:**
    - **Comments:**
    - **Example:** holographic

#### 2.12.2 GratingDensity

URI: <https://w3id.org/my-schema#PreferredLabel>
!!! note
    - **Preferred label:** gratingDensity
    - **Definition:** Number of grooves per mm on the grating; higher density offers better resolution but narrower spectral range.
    - **Data type:** integer
    - **Obligation:** mandatory
    - **Occurrences:** 1
    - **Allowed values:** free text
    - **Reference:**
    - **Comments:**
    - **Example:** 1800 line/mm

### 2.13 Aperture

URI: <https://w3id.org/my-schema#PreferredLabel>
!!! note
    - **Preferred label:** aperture
    - **Definition:** An opening in the optical path that controls the beam size and affects signal strength and resolution.
    - **Data type:** array
    - **Obligation:** recommended
    - **Occurrences:** 0–n
    - **Reference:**
    - **Comments:**

#### 2.13.1 Aperture Type

URI: <https://w3id.org/my-schema#PreferredLabel>
!!! note
    - **Preferred label:** apertureType
    - **Definition:** The form of aperture used (e.g., pinhole, slit, variable diaphragm) to define the light path.
    - **Data type:** string
    - **Obligation:** mandatory
    - **Occurrences:** 1
    - **Allowed values:** controlled list
    - **Reference:**
    - **Comments:**
    - **Example:** pinhole

#### 2.13.2 Aperture Size

URI: <https://w3id.org/my-schema#PreferredLabel>
!!! note
    - **Preferred label:** apertureSize
    - **Definition:** The physical size (e.g., in µm) of the aperture, determining how much light enters the detection system.
    - **Data type:** integer
    - **Obligation:** recommended
    - **Occurrences:** 0–1
    - **Allowed values:** free text
    - **Reference:**
    - **Comments:**
    - **Example:** 50 µm

## 3. Microscope

*The part of the Raman instrument that focuses the laser on the sample and collects scattered light.*

### 3.1 Microscope Objective

URI: <https://w3id.org/my-schema#PreferredLabel>
!!! note
    - **Preferred label:** microObjective
    - **Definition:** The lens in the microscope that focuses the laser beam and collects scattered light from a small sample area.
    - **Data type:** integer
    - **Obligation:** mandatory
    - **Occurrences:** 1
    - **Allowed values:** free text 
    - **Reference:**
    - **Comments:**
    - **Example:** 5x, 10x, 20x, 50x

### 3.2 Microscope Manufacturer

URI: <https://w3id.org/my-schema#PreferredLabel>
!!! note
    - **Preferred label:** microManufacturer
    - **Definition:** Manufacturer name of the microscope.
    - **Data type:** string
    - **Obligation:** optional
    - **Occurrences:** 0–1
    - **Allowed values:** free text
    - **Reference:**
    - **Comments:** This field can also take the persistent identifier of the manufacturer.
    - **Example:** Olympus

### 3.3 Microscope Model

URI: <https://w3id.org/my-schema#PreferredLabel>
!!! note
    - **Preferred label:** microModel
    - **Definition:** Model name of the microscope
    - **Data type:** string
    - **Obligation:** optional
    - **Occurrences:** 0–1
    - **Allowed values:** free text
    - **Reference:**
    - **Comments:** This field can also take the URLs link to the model. 
    - **Example:**  BXFM

### 3.4 Microscope Confocality

URI: <https://w3id.org/my-schema#PreferredLabel>
!!! note
    - **Preferred label:** microConfocality
    - **Definition:** The use of a pinhole or similar setup to improve depth resolution and reduce out-of-focus light.
    - **Data type:** boolean
    - **Obligation:** optional
    - **Occurrences:** 0–1
    - **Allowed values:** controlled list 
    - **Reference:**
    - **Comments:**
    - **Example:** Yes

### 3.5 Microscope Polarization

URI: <https://w3id.org/my-schema#PreferredLabel>
!!! note
    - **Preferred label:** microPolarization
    - **Definition:** The control or measurement of the polarization direction of the laser light and/or scattered Raman light at the microscopic scale. Polarization can provide additional information about molecular orientation or symmetry.
    - **Data type:** array
    - **Obligation:** Optional
    - **Occurrences:** 0–n
    - **Reference:**
    - **Comments:**

### 3.5.1 Radiation Type

URI: <https://w3id.org/my-schema#PreferredLabel>
!!! note
    - **Preferred label:** radiationType
    - **Definition:** The type of electromagnetic radiation used for excitation in Raman analysis. Incident or scattered.
    - **Data type:** string
    - **Obligation:** optional
    - **Occurrences:** 0–1
    - **Allowed values:** controlled list
    - **Reference:**
    - **Comments:**
    - **Example:** incident, scattered

### 3.5.2 Orientation

URI: <https://w3id.org/my-schema#PreferredLabel>
!!! note
    - **Preferred label:** orientation
    - **Definition:** Direction of the electric field vector of the polarized light (usually laser excitation or scattered Raman light) relative to the sample or the instrument’s reference frame.
    - **Data type:** string
    - **Obligation:** optional
    - **Occurrences:** 0–1
    - **Allowed values:** controlled list
    - **Reference:**
    - **Comments:**
    - **Example:** clockwise, counterclockwise

### 3.5.3 Degree

URI: <https://w3id.org/my-schema#PreferredLabel>
!!! note
    - **Preferred label:** degree
    - **Definition:** The extent or magnitude of polarization or orientation, often expressed as a percentage or angle, indicating how strongly light is polarized or molecules are aligned.
    - **Data type:** double
    - **Obligation:** optional
    - **Occurrences:** 0–n
    - **Allowed values:** free text
    - **Reference:**
    - **Comments:**
    - **Example:** 

## 4. Detector

*The device that captures Raman-scattered light and converts it into an electrical signal*.

### 4.1 Detector Manufacturer

URI: <https://w3id.org/my-schema#PreferredLabel>
!!! note
    - **Preferred label:** detectorManufacturer
    - **Definition:** Manufacturer name of the CCD detector
    - **Data type:** String
    - **Obligation:** Recommended
    - **Occurrences:** 0–1
    - **Allowed values:** Controlled vocabulary
    - **Reference:**
    - **Comments:**
    - **Example:** 

### 4.2 Detector Model

URI: <https://w3id.org/my-schema#PreferredLabel>
!!! note
    - **Preferred label:** detectorModel
    - **Definition:** Model name of the CCD detector
    - **Data type:** String
    - **Obligation:** Recommended
    - **Occurrences:** 0–1
    - **Allowed values:** Controlled vocabulary
    - **Reference:**
    - **Comments:**
    - **Example:** 

### 4.3 Detector Cooling

URI: <https://w3id.org/my-schema#PreferredLabel>
!!! note
    - **Preferred label:** detectorCooling
    - **Definition:** Cooling method based on the thermoelectric effect to cool the\nsensitive light detectors (CCDs)
    - **Data type:** String
    - **Obligation:** Optional
    - **Occurrences:** 0–1
    - **Allowed values:** Controlled vocabulary
    - **Reference:**
    - **Comments:**
    - **Example:** peltier, liquid nitrogen

### 4.4 Detector Cooling Temperature

URI: <https://w3id.org/my-schema#PreferredLabel>
!!! note
    - **Preferred label:** detectorCoolingTemp
    - **Definition:** The cooling temperature for the CCD detector. For example, room temperature, 200K, or -90ºC.
    - **Data type:** string
    - **Obligation:** optional
    - **Occurrences:** 0–1
    - **Reference:**
    - **Comments:**

#### 4.4.1 Temperature Value

URI: <https://w3id.org/my-schema#PreferredLabel>
!!! note
    - **Preferred label:** tempValue
    - **Definition:** The value of temperature. 
    - **Data type:** double
    - **Obligation:** optional
    - **Occurrences:** 0–1
    - **Allowed values:** free text 
    - **Reference:**
    - **Comments:**
    - **Example:** -90

#### 4.4.2 Temperature Unit

URI: <https://w3id.org/my-schema#PreferredLabel>
!!! note
    - **Preferred label:** tempUnit
    - **Definition:** The unit of temperature
    - **Data type:** string
    - **Obligation:** optional
    - **Occurrences:** 0–1
    - **Allowed values:** controlled list `[°C, °F, K]`
    - **Reference:**
    - **Comments:**
    - **Example:** °C

### 4.5 Detector Pixel

URI: <https://w3id.org/my-schema#PreferredLabel>
!!! note
    - **Preferred label:** detectorPixel
    - **Definition:** Array dimension and pixel size of the CCD detector.
    - **Data type:** string
    - **Obligation:** optional
    - **Occurrences:** 0–1
    - **Reference:**
    - **Comments:**

#### 4.5.1 Array Dimension

URI: <https://w3id.org/my-schema#PreferredLabel>
!!! note
    - **Preferred label:** arrayDimension
    - **Definition:** Expressed as horizontal × Vertical (e.g., 1024 × 256 pixels). 
    - **Data type:** string
    - **Obligation:** optional
    - **Occurrences:** 0–1
    - **Allowed values:** free text 
    - **Reference:**
    - **Comments:**
    - **Example:** 1024 × 256

#### 4.5.2 Pixel Size

URI: <https://w3id.org/my-schema#PreferredLabel>
!!! note
    - **Preferred label:** pixelSize
    - **Definition:** Width × height in micrometers (µm).
    - **Data type:** string
    - **Obligation:** optional
    - **Occurrences:** 0–1
    - **Allowed values:** free text
    - **Reference:**
    - **Comments:**
    - **Example:** 26 µm × 26 µm