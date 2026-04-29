# radix-4-BKA-booth-multiple
# Parametric Radix-4 Booth Multiplier with Brent-Kung Adder

## 🚀 Architecture
This project implements a high-efficiency hardware multiplier optimized for both area and speed.

### Features
1. **Radix-4 Booth Encoding**: Reduces the number of partial products to $N/2 + 1$.
2. **4-2 Compressor Tree**: Orchestrates the reduction of partial products with a more regular layout than 3-2 Full Adders.
3. **Brent-Kung Adder (BKA)**: A parallel-prefix adder used for the final 2-row summation, offering $O(\log N)$ delay with minimal wiring congestion.

## 📂 Project Structure
- `rtl/booth_encoder.v` - Radix-4 logic
- `rtl/compressor_tree.v` - 4-2 Compressor implementation
- `rtl/bka_adder.v` - Brent-Kung Parallel Prefix logic
- `tb/booth_multiplier_tb.v` - Self-checking testbench

## 🛠️ Verification
The design was verified using **VCS/Verdi** workflow. To run simulation:
```bash
vcs -full64 -sverilog rtl/*.v tb/*.v -debug_access+all
./simv
