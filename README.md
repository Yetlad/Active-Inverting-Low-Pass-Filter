
## Inverting Active Low-Pass Filter Design (LTspice)

---

## Objective

The objective of this exercise is to **design and verify an inverting active low-pass filter** with the following specifications:

* **DC gain** = −2
* **Bandwidth (cutoff frequency)** = 500 rad/s

The filter is implemented using an operational amplifier and verified through **AC analysis in LTspice**.

---

The transfer function of an inverting first-order active low-pass filter is:

[
H(j\omega) = \frac{-R_f}{R_1}\cdot \frac{1}{1 + j\omega R_f C}
]

From this equation:

* **DC Gain**:
  [
  A_0 = -\frac{R_f}{R_1}
  ]

* **Bandwidth**:
  [
  \omega_c = \frac{1}{R_f C}
  ]

---

## Task 1 – Filter Design

Component values are chosen to satisfy the design requirements.

### Design Conditions

* DC Gain = −2 →
  [
  \frac{R_f}{R_1} = 2
  ]

* Bandwidth = 500 rad/s →
  [
  R_f C = \frac{1}{500}
  ]

### Example Component Selection

* ( R_1 = 10,k\Omega )
* ( R_f = 20,k\Omega )
* ( C = 100,nF )

These values satisfy both the gain and bandwidth requirements.

---

## Task 2 – LTspice Circuit

### Circuit Construction

1. Place an **op-amp** (e.g., UniversalOpamp2)
2. Connect:

   * ( R_1 ) between input and inverting terminal
   * ( R_f ) in parallel with capacitor ( C ) in the feedback path
   * Non-inverting terminal to ground
3. Power the op-amp with **±12 V supplies**
4. Set the input source:

   * AC amplitude = **1 V**

---

## Task 3 – AC Analysis

### Simulation Directive

```text
.ac dec 100 1 10k
```

### Output Plot

The magnitude response is plotted using:

```text
db(V(out)/V(in))
```

This allows direct observation of the gain and cutoff frequency.

---

## Task 4 – Verification

The following points are verified from the AC plot:

1. **Passband Gain**

   * Gain ≈ **6 dB**, corresponding to a magnitude of 2

2. **Cutoff Frequency**

   * −3 dB point occurs at approximately **500 rad/s**

3. These points are marked on the frequency response plot for clarity.


---

## Conclusion

The simulated frequency response closely matches the theoretical design. The inverting active low-pass filter achieves the required DC gain of −2 and the specified bandwidth of 500 rad/s.

---


