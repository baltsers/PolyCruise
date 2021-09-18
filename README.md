# Vulnerabilities detected by polycruise (cross-language DIFA)
We evaluate polycruise on several popular open-source projects developed mainly in Python and C languages.
Eventually, 11 vulnerabilities in 5 projects below are validated to be exploitable, and corresponding PoCs are attached.

## [Bounter](https://github.com/RaRe-Technologies/bounter)
#### [Vulnerability-1]:
**Description**: With carefully constructed inputs (when the width of the hash bucket is set large enough), NULL pointer access could happen hence causing the Python to crash down.<br>
**Exploitation**: PoC: [cms_increase_47.py](https://github.com/baltsers/polycruise/blob/main/bounter/vulnerability-1/cms_increase_47.py) and [Output](https://github.com/baltsers/polycruise/blob/main/bounter/vulnerability-1/output.txt).

## [Cvxopt](https://github.com/cvxopt/cvxopt)
#### [Vulnerability-1]:
**Description**: Through carefully modify the name of a Capsule object, the PoC can easily bypass the validation in the **diag API** hence causing unexpected results (e.g., crash down during the execution of PoC).<br>
**Exploitation**: PoC: [diag_193.py](https://github.com/baltsers/polycruise/blob/main/cvxopt/vulnerability-1/diag_193.py) and [Output](https://github.com/baltsers/polycruise/blob/main/cvxopt/vulnerability-1/output.txt).
#### [Vulnerability-2]:
**Description**: Through carefully modify the name of a Capsule object, the PoC can easily bypass the validation in the **getfactor API** hence causing unexpected results (e.g., crash down during the execution of PoC).<br>
**Exploitation**: PoC: [getfactor_193.py](https://github.com/baltsers/polycruise/blob/main/cvxopt/vulnerability-2/getfactor_193.py) and [Output](https://github.com/baltsers/polycruise/blob/main/cvxopt/vulnerability-2/output.txt).
#### [Vulnerability-3]:
**Description**: Through carefully modify the name of a Capsule object, the PoC can easily bypass the validation in the **solve API** hence causing unexpected results (e.g., crash down during the execution of PoC).<br>
**Exploitation**: PoC: [solve_193.py](https://github.com/baltsers/polycruise/blob/main/cvxopt/vulnerability-3/solve_193.py) and [Output](https://github.com/baltsers/polycruise/blob/main/cvxopt/vulnerability-3/output.txt).
#### [Vulnerability-4]:
**Description**: Through carefully modify the name of a Capsule object, the PoC can easily bypass the validation in the **spsolve API** hence causing unexpected results (e.g., crash down during the execution of PoC).<br>
**Exploitation**: PoC: [spsolve_193.py](https://github.com/baltsers/polycruise/blob/main/cvxopt/vulnerability-4/spsolve_193.py) and [Output](https://github.com/baltsers/polycruise/blob/main/cvxopt/vulnerability-4/output.txt).

## [Japronto](https://github.com/squeaky-pl/japronto)
#### [Vulnerability-1]:
**Description**: When passing byte stream context into the server API Response, the server runs abnormally, throws exceptions, and fails to deals with the following requests.<br>
**Exploitation**: PoC: [feed_183_client.py](https://github.com/baltsers/polycruise/blob/main/japronto/vulnerability-1/feed_183_client.py) & [feed_183_server.py](https://github.com/baltsers/polycruise/blob/main/japronto/vulnerability-1/feed_183_server.py) and [Output](https://github.com/baltsers/polycruise/blob/main/japronto/vulnerability-1/output.txt).

## [Numpy](https://github.com/numpy/numpy)
#### [Vulnerability-1]:
**Description**: When loading a high-dimension array (larger than 32), a stack smashing error happens and causes the Python process to crash down.<br>
**Exploitation**: PoC: [array_nd_18939.py](https://github.com/baltsers/polycruise/blob/main/numpy/vulnerability-1/array_nd_18939.py) and [Output](https://github.com/baltsers/polycruise/blob/main/numpy/vulnerability-1/output.txt).
#### [Vulnerability-2]:
**Description**: When constructing a loop to create high-dimension arrays repetitively, and keeping the references of the arrays effective, an error of NULL pointer access happens hence causing the Python to crash down.<br>
**Exploitation**: PoC: [array_nil_19038.py](https://github.com/baltsers/polycruise/blob/main/numpy/vulnerability-2/array_nil_19038.py) and [Output](https://github.com/baltsers/polycruise/blob/main/numpy/vulnerability-2/output.txt).
#### [Vulnerability-3]:
**Description**: In the f2py module, when creating a high-dimension array through the **array API** (deliberately construct negative numbers in shape), an unexpected error occurs and causes Python to crash down.<br>
**Exploitation**: PoC: [array_attr_19000.py](https://github.com/baltsers/polycruise/blob/main/numpy/vulnerability-3/array_attr_19000.py) and [Output](https://github.com/baltsers/polycruise/blob/main/numpy/vulnerability-3/output.txt).

## [Pyo](https://github.com/belangeo/pyo)
#### [Vulnerability-1]:
**Description**: When testing the Pyo library with audio type "jack", the server is initialized with an overlong (over 32) string, an error of buffer overflow happens and causes Python to crash down.<br>
**Exploitation**: PoC: [boot_221.py](https://github.com/baltsers/polycruise/blob/main/pyo/vulnerability-1/boot_221.py) and [Output](https://github.com/baltsers/polycruise/blob/main/pyo/vulnerability-1/output.txt).
#### [Vulnerability-2]:
**Description**: After initializing a Pyo server, an arbitrary file name (length > 256) is passed to the **recstart API** and an error of segment fault happens hence causing Python to crash down.<br>
**Exploitation**: PoC: [restart_222.py](https://github.com/baltsers/polycruise/blob/main/pyo/vulnerability-2/restart_222.py) and [Output](https://github.com/baltsers/polycruise/blob/main/pyo/vulnerability-2/output.txt).
