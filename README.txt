DISCLAⓂ️EeeR:

If this account violates the general terms of use [https://docs.github.com/en/site-policy/github-terms/github-terms-of-service], please do not hesitate to report it!

For more information on using this repository, visit the official PascalCompiler webpage.
https://wiki.freepascal.org/Basic_Pascal_Tutorial/Compilers

For automatic deployment service TESTing, follow the link bellow.
https://www.google.com/sorry/index?continue=https://m.youtube.com/watch%3Fv%3Dvw8tnR_slMI%26list%3DRDC5KxLV9kKRQ%26index%3D2&q=EgQuemKyGLLh69IGIjACuCU1r-31aEkBSgcZRpUq3jAu-P5qL8H4axNvilYjFb_cb9QN_RYhXEabe2gu0ioyAnJSWgFD

{opinions are not welcome // 🥎NG/OK::\,u{1.F38'3}::true👎}

We operate on FACTual libraries & databases.-


*DISclaimer:
It is recommended to refrain yourself from revealing your ID BEting number مقسنس٠ي؟ ⚠️👉
             🎲👈🏿
         📦🏷️
       〽️
IP🚘🚨
||~~~~>
THE DATA IS TRACED FOR ILLEGAL PTH-crossovers, including the use of ILLOGICAL, non-FACTual semantic FRAMEWORK-layering of questionable, possibly ILLEGAL SOURCING origin

>>_1rvOocJ5S2Q5U258EYu9xP6EcZvufoZSzgPkcZYKDEiU〉

_tracing⛍
 \\ segmLayerERRsintetizi@
        بحب ثققخق2🐶
🆕🐰🚩
  |\Error02🔩
  ... somewhere خر فتث Ⓜ️℠™
      /بثحقثذسفثبيهرذث ١٩٠٥

<--------hidSegmLyr-------->

const SHA256 = require("crypto-js/sha256");

class Block {
  constructor(index, timestamp, data, previousHash = "") {
    this.index = index;
    this.timestamp = timestamp;
    this.data = data;
    this.previousHash = previousHash;
    this.hash = this.calculateHash();
  }

  calculateHash() {
    return SHA256(
      this.index +
        this.previousHash +
        this.timestamp +
        JSON.stringify(this.data)
    ).toString();
  }
}

class Blockchain {
  constructor() {
    this.chain = [this.createGenesisBlock()];
  }

  createGenesisBlock() {
    return new Block(0, new Date().toString(), "Genesis Block", "0");
  }

  getLatestBlock() {
    return this.chain[this.chain.length - 1];
  }

  addBlock(newBlock) {
    newBlock.previousHash = this.getLatestBlock().hash;
    newBlock.hash = newBlock.calculateHash();
    this.chain.push(newBlock);
  }

  isChainValid() {
    for (let i = 1; i < this.chain.length; i++) {
      const currentBlock = this.chain[i];
      const previousBlock = this.chain[i - 1];

      if (currentBlock.hash !== currentBlock.calculateHash()) {
        return false;
      }

      if (currentBlock.previousHash !== previousBlock.hash) {
        return false;
      }
    }
    return true;
  }
}

module.exports.Blockchain = Blockchain;
module.exports.Block = Block;

// Result Size [out]: 693 x 499 ‼™ 🔩🔩

const crypto = require('crypto');

// Function to hash a password
function hashPassword(password) {
  // Generate a random salt (16 bytes)
  const salt = crypto.randomBytes(16).toString('hex');

  // Use scrypt for password hashing (recommended)
  const hash = crypto.scryptSync(password, salt, 64).toString('hex');

  // Return both salt and hash for storage
  return { salt, hash };
}

// Function to verify a password
function verifyPassword(password, salt, hash) {
  const hashedPassword = crypto.scryptSync(password, salt, 64).toString('hex');
  return hashedPassword === hash;
}

// Example usage
const password = 'mySecurePassword';

// Hash the password for storage
const { salt, hash } = hashPassword(password);
console.log('Salt:', salt);
console.log('Hash:', hash);

// Verify a login attempt
const isValid = verifyPassword(password, salt, hash);
console.log('Password valid:', isValid); // true

const isInvalid = verifyPassword('wrongPassword', salt, hash);
console.log('Wrong password valid:', isInvalid); // false
