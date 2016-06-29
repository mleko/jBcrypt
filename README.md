# jBCrypt

jBCrypt is an implementation the OpenBSD Blowfish password hashing
algorithm, as described in "A Future-Adaptable Password Scheme" by Niels
Provos and David Mazieres: http://www.openbsd.org/papers/bcrypt-paper.ps

This system hashes passwords using a version of Bruce Schneier's
Blowfish block cipher with modifications designed to raise the cost of
off-line password cracking. The computation cost of the algorithm is
parameterised, so it can be increased as computers get faster.

JUnit regression tests are available in in TestBCrypt.java

jBCrypt is licensed under a ISC/BSD licence. See the LICENSE file for details.


A simple example that demonstrates most of the features:

	// Hash a password for the first time
	String hashed = BCrypt.hash(password, BCrypt.generateSalt());

	// generateSalt's log_rounds parameter determines the complexity
	// the work factor is 2**log_rounds, and the default is 10
	String hashed = BCrypt.hash(password, BCrypt.generateSalt(12));

	// Check that an unencrypted password matches one that has
	// previously been hashed
	if (BCrypt.check(candidate, hashed))
		System.out.println("It matches");
	else
		System.out.println("It does not match");

## Package notes
This is distribution of www.mindrot.org/projects/jBCrypt
It has been packaged for ease of use.