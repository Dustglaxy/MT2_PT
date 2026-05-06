# MT2_PT
# A DeepMD potential for monolayer MoTe2.
# LAMMPS input settings for a DeepMD model
"""

variable        TEMP            equal 1100
variable        kBeV            equal 8.617333262145e-5
variable        T_elec          equal ${TEMP}*${kBeV}
# ---------------------- INITIALIZAITION ------------------
units           metal
boundary        p p f
atom_style      atomic
# --------------------- ATOM DEFINITION ------------------
read_data       stru.lmp
mass            1 127.6   # Te
mass            2 95.94   # Mo

replicate 1 1 1
# --------------------- FORCE FIELDS ---------------------
pair_style      deepmd frozen_model.pb fparam ${T_elec}
pair_coeff      * *

"""
