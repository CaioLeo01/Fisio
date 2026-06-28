<script setup>
import heroClinic from './assets/images/hero-clinic.png'
import benefitsRoom from './assets/images/benefits-room.png'
import aboutClinic from './assets/images/about-clinic.png'

const specialties = [
  {
    icon: 'cross',
    title: 'Fisioterapia Ortopédica',
    description:
      'Tratamento de disfunções musculoesqueléticas, fraturas e traumas com foco na recuperação funcional.',
  },
  {
    icon: 'spark',
    title: 'Fisioterapia Esportiva',
    description:
      'Prevenção e reabilitação de lesões em atletas, otimizando o desempenho e o retorno seguro ao esporte.',
  },
  {
    icon: 'pulse',
    title: 'Pós-operatória',
    description:
      'Acompanhamento especializado após cirurgias ortopédicas para acelerar a cicatrização e mobilidade.',
  },
  {
    icon: 'posture',
    title: 'RPG',
    description:
      'Reeducação Postural Global para correção de desvios da coluna e alívio de dores posturais crônicas.',
  },
  {
    icon: 'lotus',
    title: 'Pilates Clínico',
    description:
      'Fortalecimento do core e flexibilidade através de exercícios controlados adaptados à sua condição.',
  },
  {
    icon: 'shield',
    title: 'Dor Crônica',
    description:
      'Abordagem multidisciplinar para manejo e redução de quadros de dor persistente e fibromialgia.',
  },
]

const steps = [
  {
    icon: 'clipboard',
    title: '1. Avaliação',
    description: 'Escuta atenta e exame físico detalhado para entender sua queixa.',
  },
  {
    icon: 'target',
    title: '2. Diagnóstico',
    description: 'Identificação da causa raiz do problema e metas terapêuticas.',
  },
  {
    icon: 'calendar',
    title: '3. Plano',
    description: 'Criação de um cronograma de sessões personalizado para você.',
  },
  {
    icon: 'chart',
    title: '4. Evolução',
    description: 'Monitoramento constante e ajustes para garantir o melhor resultado.',
  },
]

const benefits = [
  {
    title: 'Redução drástica de dores',
    description: 'Técnicas modernas que agem diretamente no foco do desconforto.',
  },
  {
    title: 'Melhora na flexibilidade',
    description: 'Ganho de amplitude de movimento para as tarefas do dia a dia.',
  },
  {
    title: 'Prevenção de recidivas',
    description: 'Fortalecimento preventivo para que a dor não retorne.',
  },
  {
    title: 'Vitalidade e sono melhor',
    description: 'O equilíbrio físico reflete na qualidade do seu descanso.',
  },
]

const testimonials = [
  {
    initials: 'RA',
    name: 'Ricardo Almeida',
    role: 'Paciente de Reabilitação Lombar',
    quote:
      'Cheguei na MoviCare com uma dor lombar que me impedia de trabalhar. Em poucas semanas, o tratamento humanizado e os exercícios específicos mudaram minha vida. Hoje sou maratonista e continuo vindo para manutenção.',
  },
  {
    initials: 'MS',
    name: 'Mariana Santos',
    role: 'Paciente de Pilates Clínico',
    quote:
      'O Pilates Clínico aqui é fantástico. O cuidado com a postura e a precisão dos movimentos feitos pelo instrutor me ajudaram a recuperar a flexibilidade que eu achei que tinha perdido para sempre.',
  },
  {
    initials: 'CF',
    name: 'Carla Ferreira',
    role: 'Paciente de Pós-Operatório',
    quote:
      'Excelente clínica! Fiz meu pós-operatório de joelho e me senti muito segura com toda a infraestrutura e atenção que recebi. O ambiente é muito limpo e os profissionais são incríveis.',
  },
]

const navLinks = [
  { href: '#inicio', label: 'Início' },
  { href: '#especialidades', label: 'Especialidades' },
  { href: '#sobre', label: 'Sobre' },
  { href: '#contato', label: 'Agendamento' },
]

const socialLinks = [
  { label: 'Instagram', href: '#', icon: 'instagram' },
  { label: 'Site', href: '#', icon: 'globe' },
]
</script>

<template>
  <div class="page-shell">
    <header class="site-header">
      <div class="container nav-row">
        <a class="brand" href="#inicio">MoviCare Fisioterapia</a>
        <nav class="nav-menu" aria-label="Principal">
          <a
            v-for="link in navLinks"
            :key="link.href"
            :href="link.href"
            class="nav-link"
            :class="{ active: link.href === '#inicio' }"
          >
            {{ link.label }}
          </a>
        </nav>
        <a class="button button-primary button-small desktop-cta" href="#contato">
          Agendar avaliação
        </a>
      </div>
    </header>

    <main>
      <section id="inicio" class="hero-section section">
        <div class="hero-backdrop"></div>
        <div class="container hero-grid">
          <div class="hero-copy">
            <span class="eyebrow">Excelência em Reabilitação</span>
            <h1>Recupere seus movimentos, alivie suas dores e volte a viver melhor</h1>
            <p class="hero-text">
              Atendimento fisioterapêutico personalizado para reabilitação, prevenção de
              lesões, melhora da mobilidade e qualidade de vida.
            </p>
            <div class="hero-actions">
              <a class="button button-primary" href="#contato">Agendar minha avaliação</a>
              <a class="button button-secondary" href="#especialidades">Conhecer tratamentos</a>
            </div>
            <div class="metrics-grid">
              <div class="metric">
                <strong>+10 anos</strong>
                <span>de experiência</span>
              </div>
              <div class="metric">
                <strong>Individual</strong>
                <span>atendimento humanizado</span>
              </div>
              <div class="metric">
                <strong>Foco</strong>
                <span>planos personalizados</span>
              </div>
              <div class="metric">
                <strong>Expert</strong>
                <span>profissionais especializados</span>
              </div>
            </div>
          </div>

          <div class="hero-visual">
            <div class="hero-image-card">
              <img :src="heroClinic" alt="Profissional realizando fisioterapia" />
            </div>
            <aside class="glass-card certification-card">
              <div class="icon-badge">
                <svg viewBox="0 0 24 24" aria-hidden="true">
                  <path
                    d="M12 2l2.35 4.76 5.26.76-3.8 3.7.9 5.23L12 14l-4.71 2.45.9-5.23-3.8-3.7 5.26-.76L12 2zm0 4.52L10.97 8.6l-2.3.34 1.66 1.62-.39 2.29L12 11.79l2.06 1.06-.39-2.29 1.66-1.62-2.3-.34L12 6.52z"
                  />
                </svg>
              </div>
              <div>
                <p>Clínica Certificada</p>
                <span>Padrões Internacionais</span>
              </div>
            </aside>
          </div>
        </div>
      </section>

      <section id="especialidades" class="section surface-panel">
        <div class="container">
          <div class="section-heading centered">
            <h2>Nossas Especialidades</h2>
            <p>
              Oferecemos uma gama completa de serviços focados na sua recuperação e bem-estar
              físico de forma integrada.
            </p>
          </div>

          <div class="specialties-grid">
            <article v-for="item in specialties" :key="item.title" class="specialty-card">
              <div class="specialty-icon" :data-icon="item.icon">
                <span class="icon-shape"></span>
              </div>
              <h3>{{ item.title }}</h3>
              <p>{{ item.description }}</p>
            </article>
          </div>
        </div>
      </section>

      <section class="section">
        <div class="container">
          <div class="section-heading centered">
            <h2>Seu caminho para a recuperação</h2>
          </div>

          <div class="steps-grid">
            <article v-for="step in steps" :key="step.title" class="step-card">
              <div class="step-orbit">
                <div class="step-icon" :data-icon="step.icon"></div>
              </div>
              <h3>{{ step.title }}</h3>
              <p>{{ step.description }}</p>
            </article>
          </div>
        </div>
      </section>

      <section class="section subtle-surface">
        <div class="container split-section">
          <div class="split-copy">
            <div class="section-heading">
              <h2>Cuidado completo para o seu corpo voltar ao equilíbrio</h2>
            </div>

            <ul class="benefits-list">
              <li v-for="item in benefits" :key="item.title">
                <span class="check-badge" aria-hidden="true"></span>
                <div>
                  <strong>{{ item.title }}</strong>
                  <p>{{ item.description }}</p>
                </div>
              </li>
            </ul>
          </div>

          <div class="image-frame soft-lift">
            <img :src="benefitsRoom" alt="Ambiente interno da clínica MoviCare" />
          </div>
        </div>
      </section>

      <section id="sobre" class="section">
        <div class="container split-section reverse-on-mobile">
          <div class="image-frame image-frame-large dramatic-shadow">
            <img :src="aboutClinic" alt="Interior da clínica MoviCare" />
          </div>

          <div class="split-copy">
            <div class="section-heading">
              <h2>Excelência em cada detalhe</h2>
            </div>
            <p>
              Na MoviCare, acreditamos que o corpo humano possui uma incrível capacidade de
              recuperação quando recebe o estímulo e o cuidado correto. Nossa clínica foi
              projetada para oferecer um ambiente de tranquilidade e tecnologia de ponta.
            </p>
            <p>
              Nossa equipe é formada por especialistas que buscam constante atualização em
              congressos nacionais e internacionais, garantindo as evidências científicas mais
              recentes em cada protocolo aplicado.
            </p>
            <a class="button button-tertiary" href="#depoimentos">
              Conheça nossa equipe
              <span aria-hidden="true">→</span>
            </a>
          </div>
        </div>
      </section>

      <section id="depoimentos" class="section surface-panel">
        <div class="container">
          <div class="section-heading centered">
            <h2>O que dizem nossos pacientes</h2>
          </div>

          <div class="testimonials-grid">
            <article v-for="testimonial in testimonials" :key="testimonial.name" class="testimonial-card">
              <div class="stars" aria-label="5 estrelas">
                <span v-for="star in 5" :key="star">★</span>
              </div>
              <blockquote>{{ testimonial.quote }}</blockquote>
              <div class="testimonial-author">
                <div class="avatar">{{ testimonial.initials }}</div>
                <div>
                  <strong>{{ testimonial.name }}</strong>
                  <span>{{ testimonial.role }}</span>
                </div>
              </div>
            </article>
          </div>
        </div>
      </section>

      <section id="contato" class="section final-cta-wrap">
        <div class="container">
          <div class="final-cta">
            <div class="cta-glow glow-right"></div>
            <div class="cta-glow glow-left"></div>
            <div class="cta-content">
              <h2>Dê o primeiro passo para viver sem dor</h2>
              <p>
                Estamos prontos para desenhar seu plano de recuperação personalizado. Agende
                agora sua avaliação pelo WhatsApp.
              </p>
              <a class="button button-cta" href="#contato">Agendar pelo WhatsApp</a>
              <span class="cta-note">Resposta em até 15 minutos em horário comercial.</span>
            </div>
          </div>
        </div>
      </section>
    </main>

    <footer class="site-footer">
      <div class="container footer-grid">
        <div>
          <div class="footer-brand">MoviCare</div>
          <p class="footer-copy">
            Referência em fisioterapia de alta performance e reabilitação humanizada.
          </p>
          <div class="social-links">
            <a
              v-for="link in socialLinks"
              :key="link.label"
              :href="link.href"
              class="social-link"
              :aria-label="link.label"
            >
              <span :class="['social-icon', `social-icon-${link.icon}`]"></span>
            </a>
          </div>
        </div>

        <div>
          <h3>Menu</h3>
          <ul class="footer-list">
            <li v-for="link in navLinks" :key="link.label">
              <a :href="link.href">{{ link.label }}</a>
            </li>
          </ul>
        </div>

        <div>
          <h3>Legal</h3>
          <ul class="footer-list">
            <li><a href="#">Termos de Uso</a></li>
            <li><a href="#">Política de Privacidade</a></li>
            <li><a href="#">Trabalhe Conosco</a></li>
          </ul>
        </div>

        <div>
          <h3>Contato</h3>
          <ul class="footer-list footer-contact">
            <li>Av. Paulista, 1000 - Bela Vista, SP</li>
            <li>(11) 98765-4321</li>
            <li>contato@movicare.com.br</li>
          </ul>
        </div>
      </div>
      <div class="footer-bottom container">
        <p>© 2024 MoviCare Fisioterapia. Todos os direitos reservados. CNPJ: 00.000.000/0001-00</p>
      </div>
    </footer>
  </div>
</template>
