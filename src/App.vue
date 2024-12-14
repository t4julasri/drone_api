<template>
  <div>
    <!-- Navigation -->
    <nav class="navbar navbar-expand-lg navbar-light bg-white fixed-top shadow-sm">
      <div class="container">
        <a class="navbar-brand fw-bold" href="#">
          <span class="text-primary">Saas</span>Flow
        </a>
        <button class="navbar-toggler" type="button" data-bs-toggle="collapse" data-bs-target="#navbarNav">
          <span class="navbar-toggler-icon"></span>
        </button>
        <div class="collapse navbar-collapse" id="navbarNav">
          <ul class="navbar-nav ms-auto">
            <li class="nav-item">
              <a class="nav-link" href="#features">Features</a>
            </li>
            <li class="nav-item">
              <a class="nav-link" href="#pricing">Pricing</a>
            </li>
            <li class="nav-item">
              <a class="nav-link" href="#testimonials">Testimonials</a>
            </li>
            <li class="nav-item">
              <button class="btn btn-primary ms-lg-3">Get Started</button>
            </li>
          </ul>
        </div>
      </div>
    </nav>

    <!-- Hero Section -->
    <section class="hero py-5 mt-5">
      <div class="container">
        <div class="row align-items-center min-vh-75">
          <div class="col-lg-6">
            <h1 class="display-4 fw-bold mb-3">
              Transform Your Business with Our SaaS Solution
            </h1>
            <p class="lead text-muted mb-4">
              Streamline your workflow, boost productivity, and scale your business with our innovative platform.
            </p>
            <div class="d-flex gap-3">
              <button class="btn btn-primary btn-lg">Start Free Trial</button>
              <button class="btn btn-outline-dark btn-lg">Watch Demo</button>
            </div>
          </div>
          <div class="col-lg-6">
            <img src="https://www.sf-privatebank.com/assets/images/logo/logo.png" alt="Hero Image"
              class="img-fluid rounded-3 shadow-lg" />
          </div>
        </div>
      </div>
    </section>

    <!-- Features Section -->
    <section id="features" class="py-5 bg-light">
      <div class="container">
        <div class="row text-center mb-5">
          <div class="col-lg-8 mx-auto">
            <h2 class="fw-bold mb-3">Powerful Features</h2>
            <p class="text-muted">Everything you need to manage and grow your business</p>
          </div>
        </div>
        <div class="row g-4">
          <div class="col-lg-4" v-for="feature in features" :key="feature.title">
            <div class="card border-0 h-100 shadow-sm">
              <div class="card-body p-4">
                <div class="feature-icon bg-primary bg-gradient text-white rounded-3 mb-3">
                  <i :class="feature.icon"></i>
                </div>
                <h5 class="card-title mb-3">{{ feature.title }}</h5>
                <p class="card-text text-muted">{{ feature.description }}</p>
              </div>
            </div>
          </div>
        </div>
      </div>
    </section>

    <!-- Pricing Section -->
    <section id="pricing" class="py-5">
      <div class="container">
        <div class="row text-center mb-5">
          <div class="col-lg-8 mx-auto">
            <h2 class="fw-bold mb-3">Simple, Transparent Pricing</h2>
            <p class="text-muted">Choose the plan that's right for you</p>
          </div>
        </div>
        <div class="row g-4">
          <div class="col-lg-4" v-for="plan in plans" :key="plan.name">
            <div class="card border-0 h-100 shadow-sm">
              <div class="card-body p-4">
                <h5 class="text-uppercase text-primary mb-3">{{ plan.name }}</h5>
                <h2 class="display-6 fw-bold mb-3">${{ plan.price }}</h2>
                <p class="text-muted mb-4">{{ plan.description }}</p>
                <ul class="list-unstyled mb-4">
                  <li class="mb-2" v-for="feature in plan.features" :key="feature">
                    <i class="bi bi-check2 text-primary me-2"></i>
                    {{ feature }}
                  </li>
                </ul>
                <button class="btn w-100" :class="plan.name === 'Pro' ? 'btn-primary' : 'btn-outline-primary'">
                  Choose {{ plan.name }}
                </button>
              </div>
            </div>
          </div>
        </div>
      </div>
    </section>

    <!-- Testimonials Section -->
    <section id="testimonials" class="py-5 bg-light">
      <div class="container">
        <div class="row text-center mb-5">
          <div class="col-lg-8 mx-auto">
            <h2 class="fw-bold mb-3">What Our Customers Say</h2>
            <p class="text-muted">Don't just take our word for it</p>
          </div>
        </div>
        <div class="row g-4">
          <div class="col-lg-4" v-for="testimonial in testimonials" :key="testimonial.name">
            <div class="card border-0 h-100 shadow-sm">
              <div class="card-body p-4">
                <div class="mb-3">
                  <i class="bi bi-star-fill text-warning"></i>
                  <i class="bi bi-star-fill text-warning"></i>
                  <i class="bi bi-star-fill text-warning"></i>
                  <i class="bi bi-star-fill text-warning"></i>
                  <i class="bi bi-star-fill text-warning"></i>
                </div>
                <p class="card-text mb-4">{{ testimonial.comment }}</p>
                <div class="d-flex align-items-center">
                  <img :src="testimonial.avatar" alt="Avatar" class="rounded-circle me-3" width="48" />
                  <div>
                    <h6 class="mb-0">{{ testimonial.name }}</h6>
                    <small class="text-muted">{{ testimonial.position }}</small>
                  </div>
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>
    </section>

    <!-- CTA Section -->
    <section class="py-5">
      <div class="container">
        <div class="row justify-content-center">
          <div class="col-lg-8 text-center">
            <h2 class="fw-bold mb-3">Ready to Get Started?</h2>
            <p class="lead text-muted mb-4">Join thousands of satisfied customers today</p>
            <button class="btn btn-primary btn-lg">Start Your Free Trial</button>
          </div>
        </div>
      </div>
    </section>

    <!-- Footer -->
    <footer class="py-5 bg-dark text-white">
      <div class="container">
        <div class="row g-4">
          <div class="col-lg-4">
            <h5 class="fw-bold mb-3">SaasFlow</h5>
            <p class="text-muted">Making business management easier</p>
          </div>
          <div class="col-6 col-lg-2">
            <h6 class="fw-bold mb-3">Product</h6>
            <ul class="list-unstyled">
              <li class="mb-2"><a href="#" class="text-muted text-decoration-none">Features</a></li>
              <li class="mb-2"><a href="#" class="text-muted text-decoration-none">Pricing</a></li>
              <li class="mb-2"><a href="#" class="text-muted text-decoration-none">Documentation</a></li>
            </ul>
          </div>
          <div class="col-6 col-lg-2">
            <h6 class="fw-bold mb-3">Company</h6>
            <ul class="list-unstyled">
              <li class="mb-2"><a href="#" class="text-muted text-decoration-none">About</a></li>
              <li class="mb-2"><a href="#" class="text-muted text-decoration-none">Blog</a></li>
              <li class="mb-2"><a href="#" class="text-muted text-decoration-none">Careers</a></li>
            </ul>
          </div>
          <div class="col-lg-4">
            <h6 class="fw-bold mb-3">Stay Updated</h6>
            <div class="input-group mb-3">
              <input type="email" class="form-control" placeholder="Enter your email" />
              <button class="btn btn-primary">Subscribe</button>
            </div>
          </div>
        </div>
      </div>
    </footer>
  </div>
</template>

<script>
export default {
  name: 'SaasLanding',
  data() {
    return {
      features: [
        {
          title: 'Analytics Dashboard',
          description: 'Get real-time insights into your business performance with our intuitive analytics dashboard.',
          icon: 'bi bi-graph-up'
        },
        {
          title: 'Team Collaboration',
          description: 'Work seamlessly with your team members through our collaborative workspace.',
          icon: 'bi bi-people'
        },
        {
          title: 'Automated Workflows',
          description: 'Save time and reduce errors with our powerful automation tools.',
          icon: 'bi bi-gear'
        }
      ],
      plans: [
        {
          name: 'Starter',
          price: '29',
          description: 'Perfect for small teams',
          features: [
            'Up to 5 team members',
            'Basic analytics',
            '5GB storage',
            'Email support'
          ]
        },
        {
          name: 'Pro',
          price: '99',
          description: 'Best for growing businesses',
          features: [
            'Up to 20 team members',
            'Advanced analytics',
            '50GB storage',
            'Priority support',
            'Custom integrations'
          ]
        },
        {
          name: 'Enterprise',
          price: '299',
          description: 'For large organizations',
          features: [
            'Unlimited team members',
            'Custom analytics',
            'Unlimited storage',
            '24/7 support',
            'API access',
            'Custom setup'
          ]
        }
      ],
      testimonials: [
        {
          name: 'Sarah Johnson',
          position: 'CEO, TechStart',
          comment: 'SaasFlow has transformed how we manage our business. The automation features alone have saved us countless hours.',
          avatar: 'https://robohash.org/sarah-johnson?size=48x48'
        },
        {
          name: 'Mike Thompson',
          position: 'Product Manager, GrowthCo',
          comment: 'The analytics dashboard gives us insights we never had before. It\'s become an essential part of our daily operations.',
          avatar: 'https://robohash.org/mike-thompson?size=48x48'
        },
        {
          name: 'Emily Chen',
          position: 'Founder, DesignPro',
          comment: 'The team collaboration features are outstanding. We\'ve seen a significant boost in productivity since switching to SaasFlow.',
          avatar: 'https://robohash.org/emily-cheng?size=48x48'
        }
      ]
    }
  }
}
</script>

<style scoped>
.hero {
  padding-top: 7rem;
}

.feature-icon {
  width: 48px;
  height: 48px;
  display: flex;
  align-items: center;
  justify-content: center;
  font-size: 1.5rem;
}

.min-vh-75 {
  min-height: 75vh;
}

/* Custom utility classes */
.shadow-sm {
  box-shadow: 0 .125rem .25rem rgba(0, 0, 0, .075) !important;
}

.shadow-lg {
  box-shadow: 0 1rem 3rem rgba(0, 0, 0, .175) !important;
}
</style>