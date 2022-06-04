FROM jupyter/base-notebook

# Add RUN statements to install packages as the $NB_USER defined in the base images.

# Add a "USER root" statement followed by RUN statements to install system packages using apt-get,
# change file permissions, etc.

# If you do switch to root, always be sure to add a "USER $NB_USER" command at the end of the
# file to ensure the image runs as a unprivileged user by default.
RUN pip install --quiet --no-cache-dir \
# OPENQASM
	openqasm  \
# QISKIT from IBM https://qiskit.org/
        qiskit \
# CIRQ from https://github.com/quantumlib/cirq
        cirq && \
# myQLM  https://myqlm.github.io/myqlm_specific/install.html
#        myqlm myqlm-interop \
# PyQUIL from righetti  https://github.com/rigetti/pyquil
#        pyquil \
# ProkjectQ https://projectq.readthedocs.io/en/latest/index.html
#        projectq \
#        ipykernel \
#        pylatexenc \
#        pylatex &&\
        python -m qat.magics.install && \
        fix-permissions "${CONDA_DIR}" && \
        fix-permissions "/home/${NB_USER}" 
