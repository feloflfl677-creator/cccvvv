import React, { useState } from "react";
import { motion } from "framer-motion";
import html2pdf from "html2pdf.js";
import { Configuration, OpenAIApi } from "openai";

export default function CVBuilder() {
  const [lang, setLang] = useState("ar");
  const [template, setTemplate] = useState("classic");
  const [data, setData] = useState({
    name: "",
    title: "",
    email: "",
    phone: "",
    summary: "",
    skills: "",
    experience: "",
  });

  // ======== قوالب CV =========
  const TemplateClassic = () => (
    <div className="p-6 font-serif" dir={lang === "ar" ? "rtl" : "ltr"}>
      <h1 className="text-3xl font-bold">{data.name || "اسمك هنا"}</h1>
      <h2 className="text-xl text-gray-600">{data.title}</h2>
      <p className="mt-2 text-sm">{data.email} | {data.phone}</p>
      <hr className="my-4" />
      <h3 className="font-bold">نبذة</h3>
      <p>{data.summary}</p>
      <h3 className="font-bold mt-3">المهارات</h3>
      <p>{data.skills}</p>
      <h3 className="font-bold mt-3">الخبرات</h3>
      <p>{data.experience}</p>
    </div>
  );

  const TemplateModern = () => (
    <div className="p-6 font-sans bg-gray-900 text-white rounded-2xl" dir={lang === "ar" ? "rtl" : "ltr"}>
      <h1 className="text-3xl font-extrabold">{data.name || "Your Name"}</h1>
      <p className="text-blue-400">{data.title}</p>
      <p className="text-sm mt-1">{data.email} • {data.phone}</p>
      <div className="mt-4">
        <h3 className="font-bold">Profile</h3>
        <p className="text-sm">{data.summary}</p>
      </div>
    </div>
  );

  const templates = [
    { id: "classic", name: "كلاسيك", component: TemplateClassic },
    { id: "modern", name: "مودرن", component: TemplateModern },
    // يمكن إضافة المزيد من القوالب الاحترافية هنا
  ];

  const CurrentTemplate = templates.find(t => t.id === template)?.component;

  // ======== تحميل PDF ========
  const downloadPDF = () => {
    const element = document.getElementById("cv-preview");
    html2pdf().from(element).set({ margin: 0.5, filename: `${data.name || "CV"}.pdf`, html2canvas: { scale: 2 } }).save();
  };

  // ======== AI لتوليد Summary & Skills ========
  const generateAIContent = async () => {
    const configuration = new Configuration({
      apiKey: process.env.NEXT_PUBLIC_OPENAI_API_KEY
    });
    const openai = new OpenAIApi(configuration);

    const prompt = `
اكتب ملخص احترافي وسهلة القراءة لشخص اسمه ${data.name} 
يعمل كمسمى وظيفي ${data.title} ومهاراته ${data.skills}.
`;

    const response = await openai.createCompletion({
      model: "gpt-4",
      prompt,
      max_tokens: 200,
    });

    const summary = response.data.choices[0].text.trim();
    setData({ ...data, summary });
  };

  return (
    <div className="grid grid-cols-1 md:grid-cols-2 gap-4 p-6">
      <div className="space-y-3">
        <select value={lang} onChange={e => setLang(e.target.value)} className="border rounded px-2 py-1">
          <option value="ar">العربي</option>
          <option value="en">English</option>
        </select>

        <input placeholder={lang === "ar" ? "الاسم" : "Name"} className="border p-2 w-full" onChange={e => setData({ ...data, name: e.target.value })} />
        <input placeholder={lang === "ar" ? "المسمى الوظيفي" : "Job Title"} className="border p-2 w-full" onChange={e => setData({ ...data, title: e.target.value })} />
        <input placeholder={lang === "ar" ? "البريد الإلكتروني" : "Email"} className="border p-2 w-full" onChange={e => setData({ ...data, email: e.target.value })} />
        <input placeholder={lang === "ar" ? "رقم الهاتف" : "Phone"} className="border p-2 w-full" onChange={e => setData({ ...data, phone: e.target.value })} />
        <textarea placeholder={lang === "ar" ? "نبذة مختصرة" : "Summary"} className="border p-2 w-full" onChange={e => setData({ ...data, summary: e.target.value })}></textarea>
        <textarea placeholder={lang === "ar" ? "المهارات" : "Skills"} className="border p-2 w-full" onChange={e => setData({ ...data, skills: e.target.value })}></textarea>
        <textarea placeholder={lang === "ar" ? "الخبرات" : "Experience"} className="border p-2 w-full" onChange={e => setData({ ...data, experience: e.target.value })}></textarea>

        <div className="flex gap-2">
          <select value={template} onChange={e => setTemplate(e.target.value)} className="border rounded px-2 py-1">
            {templates.map(t => <option key={t.id} value={t.id}>{t.name}</option>)}
          </select>
          <button onClick={generateAIContent} className="bg-blue-500 text-white px-4 py-2 rounded">توليد AI</button>
          <button onClick={downloadPDF} className="bg-green-500 text-white px-4 py-2 rounded">تحميل PDF</button>
        </div>
      </div>

      <motion.div
        key={template}
        id="cv-preview"
        initial={{ opacity: 0, y: 20 }}
        animate={{ opacity: 1, y: 0 }}
        transition={{ duration: 0.5 }}
        className="border p-4 rounded shadow-lg"
      >
        <CurrentTemplate />
      </motion.div>
    </div>
  );
}
