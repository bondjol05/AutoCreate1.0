const puppeteer = require('puppeteer');
const fs = require('fs').promises;
const readline = require('readline');
const crypto = require('crypto');
const faker = require('faker');
const chalk = require('chalk');

console.log('[+] ============================');
console.log('[+] TOOLS SPOTIFY AUTO CREATE');
console.log(chalk.green('[+] AUTHOR | @si_bondjol'));
console.log('[+] ============================');


// Dummy function untuk visitSpotifySignUp
async function visitSpotifySignUp() {
  // Implementasi sesuai kebutuhan
  console.log('visitSpotifySignUp function executed');
}

// Dummy function untuk checkSubscriptionTools
async function checkSubscriptionTools() {
  // Implementasi sesuai kebutuhan
  console.log('checkSubscriptionTools function executed');
}

// Main function to run the script
async function main() {
  const rl = readline.createInterface({
      input: process.stdin,
      output: process.stdout
  });

  
  rl.question('[?] CHOOSE THE TOOLS:\n[+] 1. CREATE AN ACCOUNT\n[+] 2. COOMING SOON\n\n[?] YOUR CHOISE : ', async function (choice) {
      rl.close();
      if (choice === '1') {
          await visitSpotifySignUp();
      } else if (choice === '2') {
          await checkSubscriptionTools();
      } else {
          console.log(chalk.red('[!] THE TOOL YOU ARE LOOKING FOR WAS NOT FOUND! PLEASE CHOOSE 1 OR 2'));
      }
  });
}

// Run the main function
main();






// Helper functions
function generateRandomString(length) {
    return crypto.randomBytes(length).toString('hex').slice(0, length);
  }
  
  // Generate random numbers tidak perlu diubah
  function generateRandomNumbers(length) {
    const numbers = '0123456789';
    let result = '';
    const numbersLength = numbers.length;
    for (let i = 0; i < length; i++) {
      result += numbers.charAt(Math.floor(Math.random() * numbersLength));
    }
    return result;
  }
  
  // Fungsi saveEmailToFile hanya perlu didefinisikan sekali
  function saveEmailToFile(email) {
    fs.appendFileSync('akun.txt', `${email}\n`, 'utf8');
  }
  
  // Helper function untuk menampilkan informasi sukses
  function logSuccess(message) {
      console.log(`[+] ${message}`);
    }
    
    // Helper function untuk menampilkan pertanyaan
    function logQuestion(message) {
      console.log(`[?] ${message}`);
    }
  
  // Fungsi askNumberOfAccounts tidak perlu diubah
  function askNumberOfAccounts() {
      const rl = readline.createInterface({
          input: process.stdin,
          output: process.stdout
      });
    
      return new Promise((resolve) => {
          rl.question('[?] BERAPA AKUN : ', (answer) => {
              rl.close();
              resolve(parseInt(answer));
          });
      });
    }

//////////////////////////////////////////////////////////////////////////////
//////////////////////////////////////////////////////////////////////////////
/////////////////////   MENU 1  //////////////////////////////////////////////
//////////////////////////////////////////////////////////////////////////////
//////////////////////////////////////////////////////////////////////////////
//////////////////////////////////////////////////////////////////////////////
  // Function to execute menu 1 (PILIHAN 1)
  async function visitSpotifySignUp() {
    const numberOfAccounts = await askNumberOfAccounts();
    for (let i = 0; i < numberOfAccounts; i++) {
      console.log(`[+] MEMBUAT AKUN KE-${i + 1}...`);
  
      // USER AGEN
      const userAgents = await fs.readFile('useragent.txt', 'utf-8');
      const userAgentArray = userAgents.split('\n').filter(Boolean);
  
      // Anda bisa memilih salah satu user agent dari daftar secara acak atau berurutan
      const selectedUserAgent = userAgents[Math.floor(Math.random() * userAgents.length)];
      function readDataJSON1() {
        try {
            const fs = require('fs');
          const data = JSON.parse(fs.readFileSync('data.json', 'utf8'));
          return data.Domain_akun;
        } catch (error) {
          console.error('Gagal membaca data.json:', error.message);
          process.exit(1);
        }
    }
      const browser = await puppeteer.launch({ headless: "new" });
      const page = await browser.newPage();
  
      // Mengatur user agent dari daftar yang sudah dibaca
      await page.setUserAgent(selectedUserAgent);
    
    try {
    await page.goto('https://www.spotify.com/id/signup');
  
    // Menghasilkan username
    const randomFirstName = faker.name.firstName();
    const randomLastName = faker.name.lastName();
    const domain = readDataJSON1();
    const username = `${randomFirstName}${randomLastName}${domain}`;
  
    // Mengisi formulir username/email
    await page.type('input[name="username"]', username);
    // klik Next
    const nextButton1 = await page.waitForSelector('span.ButtonInner-sc-14ud5tc-0.bhKQRg.encore-bright-accent-set', {
      visible: true,
    });
    await page.waitForTimeout(1000); // Menunggu sedikit waktu untuk event hover untuk diproses jika perlu
    await nextButton1.click();

    // Fungsi untuk membaca data dari JSON
    function readDataJSON() {
        try {
            const fs = require('fs');
          const data = JSON.parse(fs.readFileSync('data.json', 'utf8'));
          return data.password_untuk_membuat_akun;
        } catch (error) {
          console.error('Gagal membaca data.json:', error.message);
          process.exit(1);
        }
    }
    // Mengisi password
    const password1 = readDataJSON();
    await page.type('input[name="new-password"]', password1);
    // klik Next
    const nextButton2 = await page.waitForSelector('span.ButtonInner-sc-14ud5tc-0.bhKQRg.encore-bright-accent-set', {
      visible: true,
    });
    await page.waitForTimeout(1000); // Menunggu sedikit waktu untuk event hover untuk diproses jika perlu
    await nextButton2.click();
  
    // Mengisi nama depan dan nama belakang
    await page.type('input[name="displayName"]', randomFirstName);
  
    // Mengisi tanggal lahir
    await page.select('select[name="month"]', '1');
    await page.type('input[name="day"]', '01');
    await page.type('input[name="year"]', '1998');
    console.log('[+] MENCOBA MENUTUP COOKIE..');
  
    // Close Cookie
    try {
      const closeButton = await page.waitForSelector('.onetrust-close-btn-handler.onetrust-close-btn-ui.banner-close-button.ot-close-icon', { timeout: 10000 });
      if (closeButton) {
          await closeButton.click();
          console.log('[+] COOKIE BERHASIL DI TUTUP');
      }
      } catch (error) {
          console.log('');
      }
  
    // PILIH GENDER
    await page.evaluate(() => {
      document.querySelector('input[id="gender_option_male"]').click();
    });
  
    // NEXT
    const nextButton3 = await page.waitForSelector('span.ButtonInner-sc-14ud5tc-0.bhKQRg.encore-bright-accent-set', {
      visible: true,
    });
    await page.waitForTimeout(1000); // Menunggu sedikit waktu untuk event hover untuk diproses jika perlu
    await nextButton3.click();
  
    // Klik pada checkbox
    await page.click('input[id="checkbox-privacy"]');
  
    // Klik SignUp
    const nextButton4 = await page.waitForSelector('span.ButtonInner-sc-14ud5tc-0.bhKQRg.encore-bright-accent-set', {
      visible: true,
    });
    await page.waitForTimeout(1000); // Menunggu sedikit waktu untuk event hover untuk diproses jika perlu
    await nextButton4.click();
  
    // Fungsi untuk save akun
    function saveEmailToFile(username) {
      const fs = require('fs');
      fs.appendFileSync('akun.txt', username + '\n', 'utf8');
    }
    // cek keberhasilan

    await page.waitForTimeout(5000);
    const currentURL = page.url();
    if (currentURL.startsWith('https://www.spotify.com/id-id/download/')) {
        console.log(chalk.green('[+] ACCOUNT SUCCESSFULLY CREATED!'));
        console.log(chalk.green('[+] MEMNYIMPAN AKUN..'));
        saveEmailToFile(username);
        console.log(chalk.green('[+] BERHASIL'));
        console.log(`\x1b[32m[+] AKUN KE-${i + 1} TELAH SELESAI DIPROSES! EMAIL : ${username}`);
        console.log(`\x1b[32m[+] PASSWORD : ${password1}`);
        console.log('\x1b[0m[+] DATA AKUN DISIMPAN DI akun.txt');
        console.log('');
    } else {
        console.log('\x1b[31m[!] GAGAL!\x1b[0m');
    }
        // Close the current page and browser after checking
      } catch (error) {
        console.error(`\x1b[31m[!] AKUN KE-${i + 1} TIDAK BERHASIL!\x1b[0m`, error.message);
        console.log('')
      }
      await browser.close();
    }
      }
//////////////////////////////////////////////////////////////////////////////
//////////////////////////////////////////////////////////////////////////////

//////////////////////////////////////////////////////////////////////////////
//////////////////////////////////////////////////////////////////////////////
/////////////////////   MENU 2  //////////////////////////////////////////////
//////////////////////////////////////////////////////////////////////////////
//////////////////////////////////////////////////////////////////////////////
//////////////////////////////////////////////////////////////////////////////
  
  // Function to check subscription status (PILIHAN 2)
  async function checkSubscriptionTools() {
    console.log(chalk.green('[+] SILAHKAN HUBUNGI @si_bondjol UNTUK ISI MENU 2'))
     }

//////////////////////////////////////////////////////////////////////////////
//////////////////////////////////////////////////////////////////////////////
  
  

  
