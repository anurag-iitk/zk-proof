# Zero Knowledge Proof

1. Installing the circom ecosystem
2. Write the circuit
3. Compile the circuit
```circom product.circom --r1cs --wasm --sym --c```

4. Go to product_js folder & Compute the witness
```node generate_witness.js product.wasm input.json witness.wtns```

5. Proving circuit with ZK
6. Generating .zkey & export verification key
7. Generate a Proof
```snarkjs groth16 prove product_0001.zkey witness.wtns proof.json public.json```

8. Verifying a Proof
```snarkjs groth16 verify verification_key.json public.json proof.json```

9. Verifying from a Smart Contract
```snarkjs zkey export solidityverifier product_0001.zkey verifier.sol```


