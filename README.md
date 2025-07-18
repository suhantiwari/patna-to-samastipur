<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Patna ↔ Samastipur Travel Agency</title>
  <!-- Tailwind CSS via CDN -->
  <script src="https://cdn.tailwindcss.com"></script>
  <!-- React & ReactDOM -->
  <script src="https://unpkg.com/react@18/umd/react.development.js" crossorigin></script>
  <script src="https://unpkg.com/react-dom@18/umd/react-dom.development.js" crossorigin></script>
  <!-- Babel for JSX transformation -->
  <script src="https://unpkg.com/@babel/standalone/babel.min.js"></script>
  <style>
    html {
      scroll-behavior: smooth;
    }
  </style>
</head>
<body class="bg-gradient-to-br from-[#0d3b66] via-[#18a0fb] to-[#cfe9ff] min-h-screen text-gray-900">
  <div id="root"></div>

  <script type="text/babel">
    const { useState } = React;

    /* ----------------------------- Hero Section ---------------------------- */
    const Hero = () => (
      <section id="home" className="relative h-screen flex flex-col items-center justify-center text-center">
        <img
          src="https://images.unsplash.com/photo-1541417904950-7cebda9d011e?auto=format&fit=crop&w=1200&q=80"
          alt="Patna skyline"
          className="absolute inset-0 w-full h-full object-cover opacity-60"
        />
        <div className="relative z-10 max-w-3xl">
          <h1 className="text-4xl md:text-6xl font-bold text-white drop-shadow-lg">
            Patna&nbsp;↔&nbsp;Samastipur
          </h1>
          <p className="mt-4 text-xl md:text-2xl text-blue-100">
            Comfortable. Safe. Affordable.
          </p>
          <a
            href="#booking"
            className="mt-8 inline-block bg-white text-blue-700 font-semibold px-6 py-3 rounded-full shadow-lg hover:scale-105 transition"
          >
            Book Now
          </a>
        </div>
      </section>
    );

    /* ---------------------------- About Section ---------------------------- */
    const Feature = ({ icon, title }) => (
      <div className="p-6 bg-blue-50 rounded-2xl shadow">
        <div className="text-4xl">{icon}</div>
        <h3 className="mt-4 text-lg font-semibold text-blue-800">{title}</h3>
      </div>
    );

    const About = () => (
      <section id="about" className="py-16 bg-white">
        <div className="container mx-auto px-4 text-center">
          <h2 className="text-3xl font-bold text-blue-700 mb-4">Why Travel With Us?</h2>
          <p className="text-gray-600 leading-relaxed max-w-2xl mx-auto">
            We specialize exclusively in the Patna&nbsp;↔&nbsp;Samastipur corridor, offering AC &amp; Non‑AC cabs,
            tempo travellers, and premium buses. Our local drivers know every shortcut, making sure you reach safely
            and on time.
          </p>
          <div className="grid sm:grid-cols-3 gap-6 mt-10">
            <Feature icon="🚗" title="Door‑to‑Door" />
            <Feature icon="🛡️" title="Trusted &amp; Safe" />
            <Feature icon="💸" title="Transparent Pricing" />
          </div>
        </div>
      </section>
    );

    /* --------------------------- Packages Section -------------------------- */
    const packages = [
      { name: "One‑Way (Sedan)", price: "₹1,800", perks: ["AC Sedan", "Up to 4 guests"] },
      { name: "one-way (SUV)", price: "₹2,500", perks: ["AC SUV", "Up to 6 guests"] },
        name: "Premium Tempo (12‑seater)",
        price: "₹3,500",
        perks: ["comfortable seats", "Music &amp; Mic", "Mineral water"],
      },
    ];

    const PackageCard = ({ name, price, perks }) => (
      <div className="bg-white rounded-2xl shadow-lg p-6 flex flex-col items-center hover:-translate-y-1 transition">
        <h3 className="text-xl font-semibold text-blue-800">{name}</h3>
        <span className="mt-4 text-3xl font-bold text-blue-600">{price}</span>
        <ul className="mt-4 text-gray-600 space-y-1">
          {perks.map((item) => (
            <li key={item}>• {item}</li>
          ))}
        </ul>
        <a
          href="#booking"
          className="mt-6 inline-block bg-blue-600 text-white px-4 py-2 rounded-full hover:bg-blue-700 transition"
        >
          Choose
        </a>
      </div>
    );

    const Packages = () => (
      <section id="packages" className="py-16 bg-blue-50">
        <div className="container mx-auto px-4 text-center">
          <h2 className="text-3xl font-bold text-blue-700 mb-4">Popular Packages</h2>
          <div className="grid md:grid-cols-3 gap-8 mt-10">
            {packages.map((p) => (
              <PackageCard key={p.name} {...p} />
            ))}
          </div>
        </div>
      </section>
    );

    /* ------------------------- Testimonials Section ------------------------ */
    const testimonials = [
      {
        name: "Anjali",
        quote: "Seamless booking and very polite driver. Reached Samastipur in 2 hrs 15 min!",
      },
      {
        name: "Rahul",
        quote: "Clean car, fair price, and on‑time pickup. Highly recommended.",
      },
      {
        name: "Dr. Kumar",
        quote: "I travel this route weekly for work—this agency never disappoints.",
      },
    ];

    const Testimonials = () => {
      const [index, setIndex] = useState(0);
      return (
        <section id="testimonials" className="py-16 bg-white">
          <div className="container mx-auto px-4 text-center">
            <h2 className="text-3xl font-bold text-blue-700 mb-4">Happy Travellers</h2>
            <div className="relative max-w-xl mx-auto">
              <blockquote className="text-xl italic text-gray-700 min-h-[120px]">
                {`“${testimonials[index].quote}”`}
              </blockquote>
              <p className="mt-4 font-semibold text-blue-600">— {testimonials[index].name}</p>
              <button
                onClick={() => setIndex((index + 1) % testimonials.length)}
                className="absolute right-0 top-0 md:top-1/2 -translate-y-1/2 text-blue-600 hover:text-blue-800 text-2xl"
              >
                ›
              </button>
            </div>
          </div>
        </section>
      );
    };

    /* --------------------------- Gallery Section --------------------------- */
    const galleryImages = [
      "https://images.unsplash.com/photo-1526401485004-4e5297ff7f69?auto=format&fit=crop&w=600&q=60",
      "https://images.unsplash.com/photo-1508780709619-79562169bc64?auto=format&fit=crop&w=600&q=60",
      "https://images.unsplash.com/photo-1591465020666-c160553d1082?auto=format&fit=crop&w=600&q=60",
      "https://images.unsplash.com/photo-1498804103079-a6351b050096?auto=format&fit=crop&w=600&q=60",
      "https://images.unsplash.com/photo-1502899576159-f224dc2349b9?auto=format&fit=crop&w=600&q=60",
      "https://images.unsplash.com/photo-1516796181074-182eb7edc9d0?auto=format&fit=crop&w=600&q=60",
    ];

    const Gallery = () => (
      <section id="gallery" className="py-16 bg-blue-50">
        <div className="container mx-auto px-4">
          <h2 className="text-3xl font-bold text-blue-700 mb-8 text-center">Route Highlights</h2>
          <div className="grid sm:grid-cols-3 gap-4">
            {galleryImages.map((src, i) => (
              <img
                key={i}
                src={src}
                className="w-full h-56 object-cover rounded-2xl shadow hover:scale-105 transition"
                alt="Bihar scenery"
              />
            ))}
          </div>
        </div>
      </section>
    );

    /* -------------------------- Booking Form Section ----------------------- */
    const initialFormState = {
      name: "",
      phone: "",
      pickup: "Patna","samastipur"
      drop: "Samastipur","patna"
      date: "",
    };

    const BookingForm = () => {
      const [form, setForm] = useState(initialFormState);
      const [submitted, setSubmitted] = useState(false);

      const handleChange = (e) => setForm({ ...form, [e.target.name]: e.target.value });

      const handleSubmit = (e) => {
        e.preventDefault();
        if (form.name && form.phone && form.date) {
          setSubmitted(true);
          setForm(initialFormState);
        }
      };

      return (
        <section id="booking" className="py-16 bg-white">
          <div className="container mx-auto px-4 text-center">
            <h2 className="text-3xl font-bold text-blue-700 mb-4">Quick Booking</h2>
            {submitted ? (
              <p className="text-green-600 text-xl">Thank you! We'll contact you shortly.</p>
            ) : (
              <form onSubmit={handleSubmit} className="max-w-lg mx-auto grid gap-4">
                <input
                  required
                  name="name"
                  value={form.name}
                  onChange={handleChange}
                  placeholder="Full Name"
                  className="p-3 rounded-lg border"
                />
                <input
                  required
                  name="phone"
                  value={form.phone}
                  onChange={handleChange}
                  placeholder="Phone Number"
                  pattern="\d{10}"
                  className="p-3 rounded-lg border"
                />
                <div className="grid sm:grid-cols-2 gap-4">
                  <input
                    name="pickup"
                    value={form.pickup}
                    onChange={handleChange}
                    placeholder="Pickup Location"
                    className="p-3 rounded-lg border"
                  />
                  <input
                    name="drop"
                    value={form.drop}
                    onChange={handleChange}
                    placeholder="Drop Location"
                    className="p-3 rounded-lg border"
                  />
                </div>
                <input
                  required
                  type="date"
                  name="date"
                  value={form.date}
                  onChange={handleChange}
                  className="p-3 rounded-lg border"
                />
                <button className="bg-blue-600 text-white py-3 rounded-lg hover:bg-blue-700 transition">
                  Submit
                </button>
              </form>
            )}
          </div>
        </section>
      );
    };

    /* --------------------------- Contact Section --------------------------- */
    const Contact = () => (
      <section id="contact" className="py-16 bg-blue-900 text-blue-100">
        <div className="container mx-auto px-4 text-center">
          <h2 className="text-3xl font-bold mb-4">Get In Touch</h2>
          <p>
            📞 <a href="tel:+919211241677" className="underline">+91 8084606060</a>
          </p>
          <p className="mt-2">
            📱 <a href="https://wa.me/919211241677" target="_blank" className="underline">WhatsApp Chat</a>
          </p>
          <p className="mt-2">
            ✉️ <a href="mailto:info@patna-samastipur-travel.com" className="underline">info@patna-samastipur-travel.com</a>
          </p>
        </div>
      </section>
    );

    /* ---------------------------- Footer Section --------------------------- */
    const Footer = () => (
      <footer className="py-6 bg-blue-950 text-center text-blue-200">
        © {new Date().getFullYear()} Patna ↔ Samastipur Travel. All rights reserved.
      </footer>
    );

    /* ------------------------------ Main App ------------------------------- */
    const App = () => (
      <>
        <Hero />
        <About />
        <Packages />
        <Testimonials />
        <Gallery />
        <BookingForm />
        <Contact />
        <Footer />
      </>
    );

    ReactDOM.createRoot(document.getElementById("root")).render(<App />);
  </script>
</body>
</html>
