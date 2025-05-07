<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <title>Admission Form - Alone Flyer's Learning</title>
  <script src="https://cdn.tailwindcss.com"></script>
  <script src="https://cdnjs.cloudflare.com/ajax/libs/jspdf/2.5.1/jspdf.umd.min.js"></script>
  <script src="https://smtpjs.com/v3/smtp.js"></script>
  <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/5.15.3/css/all.min.css" />
  <link href="https://fonts.googleapis.com/css2?family=Segoe+UI&display=swap" rel="stylesheet" />
  <style>
    body {
      font-family: 'Segoe UI', sans-serif;
      background: linear-gradient(135deg, #e0e7ff 0%, #f4f6f8 100%);
      min-height: 100vh;
    }
    input[type="file"]::-webkit-file-upload-button {
      cursor: pointer;
      background: #3b82f6;
      color: white;
      border: none;
      padding: 0.5rem 1rem;
      border-radius: 0.375rem;
      transition: background-color 0.3s ease;
    }
    input[type="file"]::-webkit-file-upload-button:hover {
      background: #2563eb;
    }
    input[type="file"]::file-selector-button {
      cursor: pointer;
      background: #3b82f6;
      color: white;
      border: none;
      padding: 0.5rem 1rem;
      border-radius: 0.375rem;
      transition: background-color 0.3s ease;
    }
    input[type="file"]::file-selector-button:hover {
      background: #2563eb;
    }
  </style>
</head>
<body class="flex items-center justify-center p-6 min-h-screen">
  <main class="w-full max-w-3xl bg-white rounded-3xl shadow-2xl p-10 md:p-14 border border-blue-300">
    <header class="mb-10 text-center">
      <h1 class="text-4xl font-extrabold text-blue-700 tracking-wide drop-shadow-md">Alone Flyer's Learning</h1>
      <p class="mt-2 text-gray-600 text-sm md:text-base max-w-xl mx-auto">
        #39, Malviya Colony, Guda Kallan - Pali (306103) &nbsp;&bull;&nbsp; 
        <a href="mailto:malviyaclassess@gmail.com" class="text-blue-600 hover:underline">malviyaclassess@gmail.com</a> &nbsp;&bull;&nbsp; 
        <a href="tel:8696602827" class="text-blue-600 hover:underline">8696602827</a>
      </p>
    </header>

    <section class="bg-blue-50 rounded-xl border border-blue-300 p-8 shadow-inner mb-10">
      <h2 class="text-3xl font-bold text-blue-800 mb-8 border-b border-blue-300 pb-3 text-center tracking-wide">Admission Details Filling</h2>
      <form id="admissionForm" class="space-y-7" novalidate>
        <div class="grid grid-cols-1 md:grid-cols-2 gap-6">
          <div>
            <label for="studentName" class="block text-gray-700 font-semibold mb-2">NAME OF STUDENT:</label>
            <input type="text" id="studentName" name="studentName" required placeholder="Enter student's full name" class="w-full px-5 py-3 border border-gray-300 rounded-lg focus:outline-none focus:ring-2 focus:ring-blue-500 transition" />
          </div>
          <div>
            <label for="fatherName" class="block text-gray-700 font-semibold mb-2">FATHER'S NAME:</label>
            <input type="text" id="fatherName" name="fatherName" required placeholder="Enter father's full name" class="w-full px-5 py-3 border border-gray-300 rounded-lg focus:outline-none focus:ring-2 focus:ring-blue-500 transition" />
          </div>
          <div>
            <label for="motherName" class="block text-gray-700 font-semibold mb-2">MOTHER'S NAME:</label>
            <input type="text" id="motherName" name="motherName" required placeholder="Enter mother's full name" class="w-full px-5 py-3 border border-gray-300 rounded-lg focus:outline-none focus:ring-2 focus:ring-blue-500 transition" />
          </div>
          <div>
            <label for="dob" class="block text-gray-700 font-semibold mb-2">DATE OF BIRTH:</label>
            <input type="date" id="dob" name="dob" required class="w-full px-5 py-3 border border-gray-300 rounded-lg focus:outline-none focus:ring-2 focus:ring-blue-500 transition" />
          </div>
          <div>
            <label for="admissionDate" class="block text-gray-700 font-semibold mb-2">ADMISSION DATE:</label>
            <input type="date" id="admissionDate" name="admissionDate" required class="w-full px-5 py-3 border border-gray-300 rounded-lg focus:outline-none focus:ring-2 focus:ring-blue-500 transition" />
          </div>
          <div>
            <label for="studentClass" class="block text-gray-700 font-semibold mb-2">CLASS:</label>
            <select id="studentClass" name="studentClass" required onchange="calculateFees()" class="w-full px-5 py-3 border border-gray-300 rounded-lg focus:outline-none focus:ring-2 focus:ring-blue-500 transition">
              <option value="" disabled selected>Select Class</option>
              <option value="1st">1st</option>
              <option value="2nd">2nd</option>
              <option value="3rd">3rd</option>
              <option value="4th">4th</option>
              <option value="5th">5th</option>
              <option value="6th">6th</option>
              <option value="7th">7th</option>
              <option value="8th">8th</option>
              <option value="9th">9th</option>
              <option value="10th">10th</option>
            </select>
          </div>
          <div class="md:col-span-2">
            <label for="subjects" class="block text-gray-700 font-semibold mb-2">SUBJECTS:</label>
            <input type="text" id="subjects" name="subjects" required placeholder="e.g. Math, Science, English" class="w-full px-5 py-3 border border-gray-300 rounded-lg focus:outline-none focus:ring-2 focus:ring-blue-500 transition" />
          </div>
          <div>
            <label for="fees" class="block text-gray-700 font-semibold mb-2">MONTHLY FEES (IN INR):</label>
            <input type="text" id="fees" name="fees" readonly placeholder="Fees will be calculated based on class" class="w-full px-5 py-3 bg-gray-100 border border-gray-300 rounded-lg text-gray-600 font-semibold" />
          </div>
          <div>
            <label for="photo" class="block text-gray-700 font-semibold mb-2">STUDENT PHOTO (3x4 size):</label>
            <input type="file" id="photo" name="photo" accept="image/*" required class="w-full text-gray-700" />
          </div>
          <div class="md:col-span-2">
            <label for="email" class="block text-gray-700 font-semibold mb-2">Your Email (to receive form):</label>
            <input type="email" id="email" name="email" required placeholder="example@mail.com" class="w-full px-5 py-3 border border-gray-300 rounded-lg focus:outline-none focus:ring-2 focus:ring-blue-500 transition" />
          </div>
          <div class="md:col-span-2 flex items-center gap-3">
            <input type="checkbox" id="terms" name="terms" required class="w-5 h-5 text-blue-600 border-gray-300 rounded focus:ring-blue-500" />
            <label for="terms" class="text-gray-700 font-semibold select-none">I agree to all terms and conditions</label>
          </div>
        </div>

        <button type="submit" class="w-full bg-blue-600 hover:bg-blue-700 text-white font-extrabold py-4 rounded-xl transition-colors duration-300 flex items-center justify-center gap-3 text-lg shadow-lg shadow-blue-400/30">
          <i class="fas fa-download"></i> Submit & Download PDF
        </button>
      </form>
    </section>

    <section id="successMessage" class="hidden bg-green-100 border border-green-400 text-green-700 px-6 py-5 rounded-lg mb-10" role="alert">
      <p class="font-semibold text-lg">Successfully admissioned! PDF generated and form details sent to your email.</p>
      <p class="mt-3">Welcome to Alone Flyer's Learning! Please read the terms and conditions below carefully:</p>
      <ol class="list-decimal list-inside mt-3 space-y-2 text-gray-800">
        <li><strong>Attendance:</strong> Attend scheduled sessions punctually and actively participate.</li>
        <li><strong>Payment:</strong> Fees are due as agreed, ensuring continued access to coaching.</li>
        <li><strong>Respect:</strong> Treat the coach and fellow students with courtesy and respect.</li>
        <li><strong>Confidentiality:</strong> Maintain the confidentiality of shared information within the coaching group.</li>
        <li><strong>Effort:</strong> Commit to putting in the necessary effort to achieve your goals.</li>
      </ol>
    </section>
  </main>

  <script>
    function calculateFees() {
      const classVal = document.getElementById("studentClass").value;
      let fee = 0;
      if (["1st", "2nd", "3rd", "4th"].includes(classVal)) fee = 300;
      else if (["5th", "6th", "7th", "8th"].includes(classVal)) fee = 400;
      else if (["9th", "10th"].includes(classVal)) fee = 500;
      document.getElementById("fees").value = fee ? `${fee}` : "";
    }

    function formatDate(dateStr) {
      if (!dateStr) return "";
      const d = new Date(dateStr);
      return d.toLocaleDateString(undefined, { year: 'numeric', month: 'long', day: 'numeric' });
    }

    // Generate unique Student Registration Number (SRN)
    function generateSRN() {
      const prefix = "AFL2025-";
      let lastNumber = localStorage.getItem("lastSRNNumber");
      if (!lastNumber) {
        lastNumber = 0;
      } else {
        lastNumber = parseInt(lastNumber, 10);
      }
      const newNumber = lastNumber + 1;
      localStorage.setItem("lastSRNNumber", newNumber);
      // Pad number with leading zeros to 5 digits
      const paddedNumber = newNumber.toString().padStart(5, "0");
      return prefix + paddedNumber;
    }

    document.getElementById("admissionForm").addEventListener("submit", async function (e) {
      e.preventDefault();

      const studentName = document.getElementById("studentName").value.trim();
      const fatherName = document.getElementById("fatherName").value.trim();
      const motherName = document.getElementById("motherName").value.trim();
      const dob = document.getElementById("dob").value;
      const admissionDate = document.getElementById("admissionDate").value;
      const studentClass = document.getElementById("studentClass").value;
      const subjects = document.getElementById("subjects").value.trim();
      const fees = document.getElementById("fees").value;
      const email = document.getElementById("email").value.trim();
      const photoFile = document.getElementById("photo").files[0];
      const termsChecked = document.getElementById("terms").checked;

      if (!studentName || !fatherName || !motherName || !dob || !admissionDate || !studentClass || !subjects || !fees || !email || !photoFile) {
        alert("Every entry is mandatory. Please fill all fields.");
        return;
      }
      if (!termsChecked) {
        alert("You must agree to all terms and conditions to proceed.");
        return;
      }

      const srn = generateSRN();

      const reader = new FileReader();
      reader.readAsDataURL(photoFile);
      reader.onload = async function () {
        const imgData = reader.result;
        const { jsPDF } = window.jspdf;
        const doc = new jsPDF({ unit: 'pt', format: 'a4', compress: true });

        const primaryColor = '#2563eb';
        const textColor = '#1f2937';
        const labelColor = '#dc2626'; // red-600 for labels
        const borderColor = '#d1d5db';
        const lightBlue = '#e0e7ff';

        const pageWidth = doc.internal.pageSize.getWidth();
        const pageHeight = doc.internal.pageSize.getHeight();

        // Header background
        doc.setFillColor(primaryColor);
        doc.rect(0, 0, pageWidth, 70, 'F');

        // Header text
        doc.setFont('helvetica', 'bold');
        doc.setFontSize(24);
        doc.setTextColor(255, 255, 255);
        doc.text("Alone Flyer's Learning", pageWidth / 2, 45, { align: 'center' });

        // Subheader
        doc.setFontSize(11);
        doc.setFont('helvetica', 'normal');
        doc.text("#39, Malviya Colony, Guda Kallan - Pali (306103)", pageWidth / 2, 65, { align: 'center' });
        doc.text("Email: malviyaclassess@gmail.com | Phone: 8696602827", pageWidth / 2, 80, { align: 'center' });

        // Title box
        const titleBoxX = 40, titleBoxY = 100, titleBoxWidth = pageWidth - 80, titleBoxHeight = 40;
        doc.setDrawColor(borderColor);
        doc.setFillColor(lightBlue);
        doc.roundedRect(titleBoxX, titleBoxY, titleBoxWidth, titleBoxHeight, 8, 8, 'FD');

        doc.setFontSize(18);
        doc.setFont('helvetica', 'bold');
        doc.setTextColor(primaryColor);
        doc.text("Admission Form Details", pageWidth / 2, titleBoxY + 27, { align: 'center' });

        // Content start
        let y = titleBoxY + titleBoxHeight + 30;
        const lineHeight = 24;
        const labelX = 50;
        const valueX = 190;
        const maxWidth = pageWidth - valueX - 60;

        // Draw photo border
        const photoAreaX = pageWidth - 150;
        const photoAreaY = y - 15;
        const photoAreaWidth = 100;
        const photoAreaHeight = 135;
        doc.setDrawColor(borderColor);
        doc.roundedRect(photoAreaX - 10, photoAreaY - 10, photoAreaWidth + 20, photoAreaHeight + 20, 10, 10, 'D');

        function addLabelValue(label, value, yPos) {
          doc.setFont('helvetica', 'bold');
          doc.setFontSize(13);
          doc.setTextColor(labelColor);
          doc.text(label, labelX, yPos);
          doc.setFont('helvetica', 'normal');
          doc.setTextColor(textColor);
          doc.setFontSize(12);
          doc.text(value, valueX, yPos, { maxWidth });
        }

        addLabelValue("Student Reg. No.:", srn, y); y += lineHeight;
        addLabelValue("Name of Student:", studentName, y); y += lineHeight;
        addLabelValue("Father's Name:", fatherName, y); y += lineHeight;
        addLabelValue("Mother's Name:", motherName, y); y += lineHeight;
        addLabelValue("Date of Birth:", formatDate(dob), y); y += lineHeight;
        addLabelValue("Admission Date:", formatDate(admissionDate), y); y += lineHeight;
        addLabelValue("Class:", studentClass, y); y += lineHeight;
        addLabelValue("Subjects:", subjects, y); y += lineHeight;
        addLabelValue("Monthly Fees:", fees, y); y += lineHeight + 10;

        // Terms and Conditions Title
        doc.setFont('helvetica', 'bold');
        doc.setFontSize(16);
        doc.setTextColor(primaryColor);
        doc.text("Terms and Conditions:", labelX, y);
        y += lineHeight;

        // Terms list in red normal font
        const terms = [
          "Attendance: Attend scheduled sessions punctually and actively participate.",
          "Payment: Fees are due as agreed, ensuring continued access to coaching.",
          "Respect: Treat the coach and fellow students with courtesy and respect.",
          "Confidentiality: Maintain the confidentiality of shared information within the coaching group.",
          "Effort: Commit to putting in the necessary effort to achieve your goals."
        ];
        doc.setFont('helvetica', 'normal');
        doc.setFontSize(12);
        doc.setTextColor(textColor);
        terms.forEach((term, i) => {
          const text = `${i + 1}. ${term}`;
          const splitText = doc.splitTextToSize(text, pageWidth - labelX - 60);
          doc.text(splitText, labelX + 10, y);
          y += splitText.length * 16;
        });

        // Add student photo
        const imgWidth = 90;
        const imgHeight = 120;
        try {
          doc.addImage(imgData, 'JPEG', photoAreaX, photoAreaY, imgWidth, imgHeight);
        } catch {
          try {
            doc.addImage(imgData, 'PNG', photoAreaX, photoAreaY, imgWidth, imgHeight);
          } catch {}
        }

        // Footer line and text
        doc.setDrawColor(borderColor);
        doc.line(40, pageHeight - 70, pageWidth - 40, pageHeight - 70);
        doc.setFontSize(10);
        doc.setFont('helvetica', 'italic');
        doc.setTextColor('#6b7280');
        const footerText = "Alone Flyer's Learning - #39, Malviya Colony, Guda Kallan - Pali (306103) | Email: malviyaclassess@gmail.com | Phone: 8696602827";
        doc.text(footerText, pageWidth / 2, pageHeight - 50, { align: 'center' });

        const pdfName = `${studentName.replace(/\s+/g, "_")}_AdmissionForm.pdf`;
        doc.save(pdfName);

        const emailBody = `
          <div style="font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif; color:#1f2937;">
            <h2 style="color:#2563eb; font-weight:bold; border-bottom: 2px solid #2563eb; padding-bottom: 6px;">Admission Form - Alone Flyer's Learning</h2>
            <p><strong>Student Reg. No.:</strong> ${srn}</p>
            <p><strong>Name of Student:</strong> ${studentName}</p>
            <p><strong>Father's Name:</strong> ${fatherName}</p>
            <p><strong>Mother's Name:</strong> ${motherName}</p>
            <p><strong>Date of Birth:</strong> ${formatDate(dob)}</p>
            <p><strong>Admission Date:</strong> ${formatDate(admissionDate)}</p>
            <p><strong>Class:</strong> ${studentClass}</p>
            <p><strong>Subjects:</strong> ${subjects}</p>
            <p><strong>Monthly Fees:</strong> ${fees}</p>
            <p><strong>Student Photo:</strong></p>
            <img src="${imgData}" alt="Student photo 3x4 size" style="width:90px; height:120px; object-fit:cover; border:1px solid #ccc; border-radius: 6px;"/>
            <hr style="margin: 20px 0; border-color: #2563eb;" />
            <p>Thank you for submitting the admission form at Alone Flyer's Learning.</p>
            <p>If you have any questions, please contact us at <a href="mailto:malviyaclassess@gmail.com" style="color:#2563eb;">malviyaclassess@gmail.com</a> or call 8696602827.</p>
            <p><em>This is an automated email.</em></p>
          </div>
        `;

        try {
          await Email.send({
            SecureToken: "f3a7a7a3-3a3a-4a3a-9a3a-3a3a3a3a3a3a",
            To: email,
            From: "malviyaclassess@gmail.com",
            Subject: "Admission Form - Alone Flyer's Learning",
            Body: emailBody,
          });
          const successSection = document.getElementById("successMessage");
          successSection.classList.remove("hidden");
          successSection.scrollIntoView({ behavior: "smooth" });
          document.getElementById("admissionForm").reset();
          document.getElementById("fees").value = "";
        } catch {
          const successSection = document.getElementById("successMessage");
          successSection.classList.remove("hidden");
          successSection.querySelector("p.font-semibold").textContent = "Successfully admissioned! PDF generated successfully! But failed to send email. Please check your email address and try again.";
          successSection.scrollIntoView({ behavior: "smooth" });
          document.getElementById("admissionForm").reset();
          document.getElementById("fees").value = "";
        }
      };
    });
  </script>
</body>
</html>
