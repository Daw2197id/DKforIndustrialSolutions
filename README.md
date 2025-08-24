import { useState } from "react";
import { motion } from "framer-motion";
import {
  Car,
  Wrench,
  Cpu,
  Cable,
  BatteryCharging,
  Sparkles,
  Settings2,
  PlugZap,
  Phone,
  Mail,
  MapPin,
  CalendarCheck,
  ShieldCheck,
  ChevronRight,
} from "lucide-react";

export default function Site() {
  const [sent, setSent] = useState(false);

  const services = [
    {
      title: "Naprawy aut elektrycznych (EV/HEV)",
      desc:
        "Diagnostyka wysokonapięciowa, układy ładowania, BMS, problemy z zasięgiem i błędami HV.",
      Icon: BatteryCharging,
      items: ["Diagnoza HV", "Konserwacja pakietów", "Usterki ładowania"],
    },
    {
      title: "Aktualizacje i retrofit (CarPlay/AA)",
      desc:
        "Wdrażamy Apple CarPlay/Android Auto, aktualizujemy mapy i oprogramowanie, odblokowujemy ukryte funkcje.",
      Icon: PlugZap,
      items: ["CarPlay/Android Auto", "Akt. map i softu", "Kodowanie funkcji"],
    },
    {
      title: "Montaż ambient i dodatków",
      desc:
        "Profesjonalny montaż oświetlenia ambient, kamer cofania, czujników, nagłośnienia i innych akcesoriów.",
      Icon: Sparkles,
      items: ["Ambient RGB", "Kamery/czujniki", "Audio i akcesoria"],
    },
    {
      title: "Naprawa elektroniki",
      desc:
        "Sterowniki silnika/komfortu, moduły, liczniki, sieci CAN/LIN, programowanie i lutowanie precyzyjne.",
      Icon: Cpu,
      items: ["ECU/BCM/ABS", "CAN/LIN", "Programowanie"],
    },
    {
      title: "Wiązka po swapie",
      desc:
        "Kompletne podłączenie i uruchomienie instalacji po SWAP-ie silnika/napędu, schematy i kodowanie.",
      Icon: Cable,
      items: ["Projekt wiązki", "Podłączenie", "Kodowanie sterowników"],
    },
    {
      title: "Diagnostyka komputerowa",
      desc:
        "Zaawansowane skanery OBD, testy elementów wykonawczych, logi, adaptacje i kasowanie błędów.",
      Icon: Settings2,
      items: ["OBD II/UDS", "Testy i logi", "Adaptacje"],
    },
  ];

  const steps = [
    { n: 1, title: "Kontakt", desc: "Zadzwoń lub wypełnij formularz." },
    { n: 2, title: "Diagnostyka", desc: "Wstępna wycena po odczycie błędów." },
    { n: 3, title: "Potwierdzenie", desc: "Ustalamy kosztorys i termin." },
    { n: 4, title: "Realizacja", desc: "Naprawa/retrofit zgodnie ze sztuką." },
    { n: 5, title: "Odbiór i gwarancja", desc: "Test drogowy i pisemna gwarancja." },
  ];

  function handleSubmit(e) {
    e.preventDefault();
    const data = Object.fromEntries(new FormData(e.currentTarget).entries());
    console.log("Nowe zgłoszenie:", data);
    setSent(true);
    e.currentTarget.reset();
  }

  return (
    <div className="min-h-screen bg-slate-950 text-slate-100">
      {/* NAV */}
      <header className="sticky top-0 z-50 backdrop-blur supports-[backdrop-filter]:bg-slate-950/60 border-b border-white/10">
        <div className="mx-auto max-w-7xl px-4 py-3 flex items-center justify-between">
          <a href="#hero" className="flex items-center gap-2 group">
            <div className="p-2 rounded-xl bg-sky-500/10 ring-1 ring-sky-400/30 group-hover:ring-sky-300 transition">
              <Car className="h-5 w-5 text-sky-300" />
            </div>
            <div className="leading-tight">
              <p className="font-semibold tracking-wide">Auto Upgrade Lab</p>
              <p className="text-xs text-slate-400">Elektronika • Retrofit • EV</p>
            </div>
          </a>
          <nav className="hidden md:flex gap-6 text-sm">
            <a href="#uslugi" className="hover:text-sky-300">Usługi</a>
            <a href="#proces" className="hover:text-sky-300">Proces</a>
            <a href="#realizacje" className="hover:text-sky-300">Realizacje</a>
            <a href="#faq" className="hover:text-sky-300">FAQ</a>
            <a href="#kontakt" className="hover:text-sky-300">Kontakt</a>
          </nav>
          <div className="flex items-center gap-3">
            <a
              href="#kontakt"
              className="hidden md:inline-flex items-center gap-2 rounded-2xl bg-sky-500/90 hover:bg-sky-400 px-4 py-2 text-sm font-semibold shadow-lg shadow-sky-500/20"
            >
              <Phone className="h-4 w-4" /> Umów wizytę
            </a>
          </div>
        </div>
      </header>

      {/* HERO */}
      <section id="hero" className="relative overflow-hidden">
        <div className="pointer-events-none absolute inset-0 bg-[radial-gradient(60%_60%_at_50%_-10%,rgba(14,165,233,0.25),rgba(2,6,23,0))]" />
        <div className="mx-auto max-w-7xl px-4 py-20 md:py-28 grid md:grid-cols-2 gap-10 items-center">
          <motion.div initial={{ opacity: 0, y: 12 }} animate={{ opacity: 1, y: 0 }} transition={{ duration: 0.6 }}>
            <h1 className="text-3xl md:text-5xl font-bold leading-tight">
              Naprawy aut elektrycznych i elektroniki samochodowej
            </h1>
            <p className="mt-4 text-slate-300 md:text-lg">
              CarPlay/Android Auto, montaż ambient, kodowanie i diagnostyka CAN. Profesjonalnie, z gwarancją.
            </p>
            <div className="mt-6 flex flex-wrap gap-3">
              <a href="#uslugi" className="inline-flex items-center gap-2 rounded-2xl bg-white/10 hover:bg-white/15 px-4 py-2 text-sm ring-1 ring-white/10">
                Zobacz usługi <ChevronRight className="h-4 w-4" />
              </a>
              <a href="#kontakt" className="inline-flex items-center gap-2 rounded-2xl bg-sky-500/90 hover:bg-sky-400 px-4 py-2 text-sm font-semibold shadow-lg shadow-sky-500/20">
                Umów konsultację <CalendarCheck className="h-4 w-4" />
              </a>
            </div>
            <div className="mt-6 flex flex-wrap items-center gap-4 text-xs text-slate-400">
              <div className="flex items-center gap-2"><ShieldCheck className="h-4 w-4" /> Gwarancja pisemna</div>
              <div className="flex items-center gap-2"><Wrench className="h-4 w-4" /> OEM standard montażu</div>
              <div className="flex items-center gap-2"><Cpu className="h-4 w-4" /> Diagnostyka klasy serwisowej</div>
            </div>
          </motion.div>

          <motion.div initial={{ opacity: 0, y: 12 }} animate={{ opacity: 1, y: 0 }} transition={{ duration: 0.8, delay: 0.1 }}>
            <div className="relative">
              <div className="absolute -inset-4 bg-gradient-to-tr from-sky-500/20 via-fuchsia-500/10 to-transparent blur-2xl" />
              <div className="relative rounded-3xl ring-1 ring-white/10 bg-white/5 p-6 md:p-8 shadow-2xl">
                <div className="grid grid-cols-2 gap-4">
                  {[
                    { Icon: BatteryCharging, label: "EV/HEV" },
                    { Icon: PlugZap, label: "CarPlay" },
                    { Icon: Sparkles, label: "Ambient" },
                    { Icon: Cpu, label: "ECU/BCM" },
                  ].map(({ Icon, label }, i) => (
                    <div key={i} className="aspect-video rounded-2xl bg-slate-900/60 ring-1 ring-white/10 flex flex-col items-center justify-center gap-2 hover:ring-sky-400/40 transition">
                      <Icon className="h-7 w-7" />
                      <span className="text-sm text-slate-300">{label}</span>
                    </div>
                  ))}
                </div>
                <div className="mt-6 rounded-2xl bg-slate-900/60 ring-1 ring-white/10 p-4 text-sm text-slate-300">
                  Specjalizacja w markach europejskich (m.in. BMW — E/F/G),
                  retrofit CarPlay oraz serwis wiązek po SWAP-ie.
                </div>
              </div>
            </div>
          </motion.div>
        </div>
      </section>

      {/* ...usługi, proces, realizacje, FAQ bez zmian... */}

      {/* CONTACT */}
      <section id="kontakt" className="mx-auto max-w-7xl px-4 py-16 md:py-24">
        <div className="grid lg:grid-cols-3 gap-8 items-start">
          <div className="lg:col-span-2">
            <h2 className="text-2xl md:text-3xl font-semibold">Skontaktuj się</h2>
            <p className="mt-2 text-slate-300 max-w-prose">
              Opisz usterkę lub planowany retrofit. Odpowiemy z wyceną i najbliższym terminem.
            </p>
            {/* formularz zostaje bez zmian */}
          </div>

          <aside className="rounded-3xl bg-white/5 ring-1 ring-white/10 p-6">
            <h3 className="font-semibold">Dane kontaktowe</h3>
            <div className="mt-4 grid gap-3 text-sm">
              <p className="flex items-center gap-2"><Phone className="h-4 w-4" /> <a href="tel:+48788929991" className="hover:underline">+48 788 929 991</a></p>
              <p className="flex items-center gap-2"><Mail className="h-4 w-4" /> <a href="mailto:biuro@autoupgradelab.pl" className="hover:underline">biuro@autoupgradelab.pl</a></p>
              <p className="flex items-center gap-2"><MapPin className="h-4 w-4" /> Wola Jachowa 62A, Polska</p>
            </div>
            <div className="mt-6 rounded-2xl bg-slate-900/60 ring-1 ring-white/10 p-4 text-sm text-slate-300">
              <p className="font-medium">Godziny</p>
              <p>Pon–Pt 9:00–18:00 • Sob 10:00–14:00</p>
              <p className="mt-3 text-xs text-slate-400">Możliwość odbioru/zwrotu auta poza godzinami — zapytaj.</p>
            </div>
          </aside>
        </div>
      </section>

      {/* FOOTER */}
      <footer className="border-t border-white/10">
        <div className="mx-auto max-w-7xl px-4 py-10 flex flex-col md:flex-row items-center justify-between gap-4">
          <p className="text-sm text-slate-400">© {new Date().getFullYear()} Auto Upgrade Lab. Wszelkie prawa zastrzeżone.</p>
          <div className="flex items-center gap-5 text-sm">
            <a href="#uslugi" className="hover:text-sky-300">Usługi</a>
            <a href="#faq" className="hover:text-sky-300">FAQ</a>
            <a href="#kontakt" className="hover:text-sky-300">Kontakt</a>
          </div>
        </div>
      </footer>

      {/* FLOATING CTA */}
      <a
        href="#kontakt"
        className="fixed bottom-4 right-4 md:bottom-6 md:right-6 inline-flex items-center gap-2 rounded-2xl bg-sky-500/90 hover:bg-sky-400 px-4 py-2 text-sm font-semibold shadow-xl shadow-sky-500/30"
      >
        <Phone className="h-4 w-4" /> Zadzwoń: 788 929 991
      </a>
    </div>
  );
}
