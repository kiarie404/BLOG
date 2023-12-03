
1. **What is the definition of nanotechnology?**  
   manipulating things at nanoscale to do whatever. Typically, manipulating materials with the atom being the basic unit of manipulation.   

2. **The number 1,234,567 written out is one million, two hundred thirty-four thousand, five hundred sixty seven. Write out this number: 1,200,300,400,500,600,700,800,901.**
    1 septillion, two hundred sextillion, three hundred quantillion, four hundred quadrillion, five hundred trillion, six hundred billion,
    seven hundred million, eight hundred thousand, nine hundred and one.    

3. **Rank the following things from largest to smallest: polio virus, drop of water, mercury atom, Escherichia coli bacterium, helium atom, human red blood cell.**  
   - drop of water
   - Escherichia coli bacterium
   - human red blood cell
   - polio virus
   - mercury atom
   - helium atom

4. **Approximately how long ago was the concept of the atom introduced?**  I do not know... during Democratus' time.    

5. **What are the three main components of an atom?**   
   Protons, neutrons, electrons

6. **What are the main components of an atom’s nucleus?**   
   Protons, neutrons

7. **What is the law of definite proportions?**  
   There are no decimals in the ratio in which atoms create molecules.   
   
8. **What is the law of multiple proportions?** 

9. **Boyle’s law states that PV = C, where P is the pressure of a gas, V is the volume, and C is a constant (assuming constant temperature). Consider a gas held in a 4-m 3 container at 1 kPa. The volume is then slowly doubled.**
   1.  **What is the new pressure?** 0.5 kPa
   2.  **Use atoms to explain how a larger container leads to a lower pressure.** bigger spaces leads to less intense repulsion among the enclosed atoms. Less intense repulsion means less intense hits by the atoms to the enclosing container.   

10. **What is the mass of a square piece of aluminum foil 100 μm thick and 10 cm wide (aluminum = 2.7 g/cm 3 )?**   
    ```rust
    {
        width_in_cm = (100 * 10^-6) * 10;
        volume_of_foil = width_in_cm * 10 * 10; // equals 10^-1 cm^3

        // if 1 cm3 contains 2.7 g of aluminium... then 
        grams_in_current_volume = volume_of_foil * 2.7 g; // = 0.27g
    }

    ```

11. **How many atoms are in the piece of foil (aluminum = 27 g/mol)?**  
    ```rust
        27g = 6.02 * 10^23 atoms
        0.27g = (0.27 * 6.02 * 10^23) / 27 = 6.02 * 10^21 atoms
    ```

12. **Calculate the mass of an atom of**    
        **a. Hydrogen (1.0 g/mol)**  
          1/(6.02 * 10^23)

        b. Silver (107.87 g/mol)
          107.87/(6.02 * 10^23)

        c. Silicon (28.09 g/mol)
          28.09/(6.02 * 10^23)

13. **What are the mass ratios of the elements in these chemical compounds? (Note: nitrogen = 14 g/mol; hydrogen = 1 g/mol; carbon = 12 g/mol; oxygen = 16 g/mol.)**

a. Ammonia, NH 3

    ```rust
    let AVG_CONST = 6.02 * 10^23;
    let mass_of_nitrogen_atom = 14 / AVG_CONST;
    let mass_of_hydrogen_atom = 1 / AVG_CONST;

    let mass_of_ammonia = mass_of_nitrogen_atom + (3 * mass_of_hydrogen_atom);
    let nitrogen_mass_ratio = (1 * mass_of_nitrogen_atom)/ mass_of_ammonia;
    let hydronen_mass_ratio = (3 * mass_of_hydrogen_atom)/ mass_of_ammonia;
    let ratio(N, H) = (nitrogen_mass_ratio, hydronen_mass_ratio )
    ```

b. Ethanol, C 2 H 6 O
c. Toluene, C 7 H 8
    

   