# dip_paper
### 5.2.2 Important Noise Probability Density Functions (PDFs)

Noise in images is often modeled using probability density functions (PDFs), which describe the statistical behavior of noise intensity values. Some common PDFs used in image processing are:

1. **Gaussian Noise:**
   - **PDF:** \( p(z) = \frac{1}{\sqrt{2 \pi \sigma^2}} e^{-\frac{(z - \mu)^2}{2\sigma^2}} \)
   - **Description:** Frequently used due to its mathematical tractability. It models electronic and sensor noise.
   - **Characteristics:** 70% of values are within \( \mu \pm \sigma \), and 95% are within \( \mu \pm 2\sigma \).

2. **Rayleigh Noise:**
   - **PDF:** \( p(z) = \frac{z - a}{b^2} e^{-\frac{(z - a)^2}{2b^2}} \) (for \( z \geq a \))
   - **Description:** Models noise with a right-skewed distribution, useful in range imaging.
   - **Characteristics:** Often used for noise with a peak displacement from the origin.

3. **Erlang (Gamma) Noise:**
   - **PDF:** \( p(z) = \frac{a^b z^{b-1} e^{-a z}}{(b-1)!} \) for \( z \geq 0 \)
   - **Description:** A special case of the gamma distribution, often used for laser imaging.
   - **Characteristics:** Defined by a positive integer \( b \), with a mean and variance related to \( a \) and \( b \).

4. **Exponential Noise:**
   - **PDF:** \( p(z) = a e^{-a z} \) for \( z \geq 0 \)
   - **Description:** A special case of Erlang noise with \( b = 1 \).
   - **Characteristics:** Models decay processes, often seen in simple systems like photon counts.

5. **Uniform Noise:**
   - **PDF:** \( p(z) = \frac{1}{b - a} \) for \( a \leq z \leq b \)
   - **Description:** Models random noise with uniform distribution over a given range.
   - **Characteristics:** Simple and used in simulations, with equal likelihood of all intensities.

6. **Impulse (Salt-and-Pepper) Noise:**
   - **PDF:** \( p(z) = P_a \) for \( z = a \) and \( p(z) = P_b \) for \( z = b \)
   - **Description:** Occurs due to sudden transients or faulty switching. Appears as black and white dots.
   - **Characteristics:** Extreme pixel values (either 0 or 255 in an 8-bit image) scattered randomly.

### Applications and Observations:
- **Gaussian Noise:** Arises due to electronic or sensor noise, common in low-light or high-temperature conditions.
- **Rayleigh Noise:** Models noise in range imaging systems.
- **Erlang (Gamma) Noise:** Used in laser imaging systems.
- **Exponential Noise:** Found in decay processes or photon counting.
- **Uniform Noise:** Often used in random number generators for simulations.
- **Impulse Noise:** Seen in digital transmission errors or faulty sensors, causing black-and-white "salt-and-pepper" effects.

### Noise Histograms and Visual Analysis:
- Histograms of noisy images (such as Gaussian, Rayleigh, Gamma) can visually reflect the type of noise, often showing merged intensity values or distinct peaks depending on the noise type.
- Impulse noise is easily recognizable by its salt-and-pepper appearance, while other types of noise like Gaussian or Rayleigh are harder to distinguish visually but show distinct patterns in their histograms.

### Estimation of Noise Parameters:
- Parameters can be estimated by analyzing image regions with constant intensity (e.g., flat backgrounds).
- For Gaussian noise, the mean and variance are sufficient.
- For impulse noise, the probability of extreme pixel values (black and white) can be estimated from the histogram of a flat region.

