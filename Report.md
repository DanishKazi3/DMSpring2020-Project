#DM 103347: RSA

###Project Members###

StdID | Name

**61903**|**Danish Kazi**

61885 | Danial Ahmed

##Project Description##
RSA is an algorithm used by modern computers to encrypt and decrypt messages. It is an asymmetric cryptographic algorithm.The algorithm is based on the fact that finding the factors of a large composite number is difficult when the factors are prime number
we aim to deliver the encryption and decryption of the messages in order to simulate.

##Discrete Mathematics Concept used##
we have used set concept in key generator class as well as logics are also used and permutation 
where as, public and private keys are involved, the fact it is helping to work is by converting the ratio of messages into the int form as prime numbers are difficult to composite.

##Example 1:Primality test##
A code of conduct is acquired on the basis of primality test where condition useing crypto service is retrieved.
public bool MillerRabinTest(int k)               
        {
            if (result == 2 || result == 3)
                return true;
            if (result < 2 || result % 2 == 0)
                return false;

            BigInteger d = result - 1;
            int s = 0;

            while (d % 2 == 0)
            {
                d /= 2;
                s += 1;

            }

            for (int i = 0; i < k; i++)
            {
                RNGCryptoServiceProvider rng = new RNGCryptoServiceProvider();
                byte[] _a = new byte[result.ToByteArray().LongLength];
                BigInteger a;

                do
                {
                    rng.GetBytes(_a);
                    a = new BigInteger(_a);
                }
                while (a < 2 || a >= result - 2);

                BigInteger x = BigInteger.ModPow(a, d, result);

                if (x == 1 || x == result - 1)
                    continue;

                for (int r = 1; r < s; r++)
                {
                    x = BigInteger.ModPow(x, 2, result);

                    if (x == 1)
                        return false;
                    if (x == result - 1)
                        break;
                }

                if (x != result - 1)  
                    return false;
            }
            return true;
        }

##Problems faced##
The major problem we faced during this project was the concepts and the alignments of them as the project was not that difficult but the concepts alignment were not easy to measure as it required basic concepts knowledge to cover up the project it was one of the biggest challenge we encounter during this project.

##References##
- https://www.youtube.com/watch?v=EA5jF_7FteM
- Google
- StackOverflow
- Youtube
