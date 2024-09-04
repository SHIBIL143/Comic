function toggleText(element) {
    const moreText = element.previousElementSibling.querySelector('.more-text');
    
    if (moreText.style.display === "none" || moreText.style.display === "") {
        moreText.style.display = "inline";
        element.textContent = "Read Less";
    } else {
        moreText.style.display = "none";
        element.textContent = "Read More";
    }
}




const express = require('express');
const bodyParser = require('body-parser');
const nodemailer = require('nodemailer');
const path = require('path');

const app = express();

// Middleware
app.use(bodyParser.urlencoded({ extended: false }));
app.use(bodyParser.json());

// Serve static files from the "public" directory
app.use(express.static(path.join(__dirname, 'public')));

// Email sending route
app.post('/send-email', (req, res) => {
    const { name, email, message } = req.body;

    let transporter = nodemailer.createTransport({
        service: 'Gmail',
        auth: {
            user: 'novasmpsrv@gmail.com',
            pass: '@SHIBILSANU@6238910801@',
        },
    });

    let mailOptions = {
        from: 'novasmpsrv@gmail.com',
        to: 'shibilsanu6238@gmail.com',
        subject: 'New Message from Comics Story Hub',
        text: `Name: ${name}\nEmail: ${email}\nMessage: ${message}`,
    };

    transporter.sendMail(mailOptions, (error, info) => {
        if (error) {
            return res.status(500).send('Error occurred while sending email');
        }
        res.status(200).send('Email sent successfully');
    });
});

// Start server
app.listen(3000, () => {
    console.log('Server is running on port 3000');
});
