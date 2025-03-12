<template>
    <div class="min-h-screen bg-gray-50 py-8">
      <div class="container mx-auto px-4 max-w-6xl">
        <h1 class="text-2xl font-bold text-gray-900 mb-8">Checkout</h1>
        
        <div class="grid grid-cols-1 gap-8">
          <!-- Checkout Form -->
          <div>
            <div class="bg-white rounded-lg shadow p-6 mb-6">
              <h2 class="text-lg font-medium text-gray-900 mb-4">Contact Information</h2>
              <div class="grid grid-cols-1 md:grid-cols-2 gap-4 mb-6">
                <div>
                  <label for="firstName" class="block text-sm font-medium text-gray-700 mb-1">First Name</label>
                  <input 
                    type="text" 
                    id="firstName" 
                    v-model="form.firstName" 
                    class="w-full px-3 py-2 border border-gray-300 rounded-md focus:outline-none focus:ring-2 focus:ring-primary"
                  />
                </div>
                <div>
                  <label for="lastName" class="block text-sm font-medium text-gray-700 mb-1">Last Name</label>
                  <input 
                    type="text" 
                    id="lastName" 
                    v-model="form.lastName" 
                    class="w-full px-3 py-2 border border-gray-300 rounded-md focus:outline-none focus:ring-2 focus:ring-primary"
                  />
                </div>
                <div>
                  <label for="email" class="block text-sm font-medium text-gray-700 mb-1">Email</label>
                  <input 
                    type="email" 
                    id="email" 
                    v-model="form.email" 
                    class="w-full px-3 py-2 border border-gray-300 rounded-md focus:outline-none focus:ring-2 focus:ring-primary"
                  />
                </div>
                <div>
                  <label for="phone" class="block text-sm font-medium text-gray-700 mb-1">Phone</label>
                  <input 
                    type="tel" 
                    id="phone" 
                    v-model="form.phone" 
                    class="w-full px-3 py-2 border border-gray-300 rounded-md focus:outline-none focus:ring-2 focus:ring-primary"
                  />
                </div>
              </div>
  
              <h2 class="text-lg font-medium text-gray-900 mb-4">Shipping Address</h2>
              <div class="space-y-4 mb-6">
                <div>
                  <label for="address" class="block text-sm font-medium text-gray-700 mb-1">Address</label>
                  <input 
                    type="text" 
                    id="address" 
                    v-model="form.address" 
                    class="w-full px-3 py-2 border border-gray-300 rounded-md focus:outline-none focus:ring-2 focus:ring-primary"
                  />
                </div>
                <div class="grid grid-cols-1 md:grid-cols-3 gap-4">
                  <div>
                    <label for="city" class="block text-sm font-medium text-gray-700 mb-1">City</label>
                    <input 
                      type="text" 
                      id="city" 
                      v-model="form.city" 
                      class="w-full px-3 py-2 border border-gray-300 rounded-md focus:outline-none focus:ring-2 focus:ring-primary"
                    />
                  </div>
                  <div>
                    <label for="state" class="block text-sm font-medium text-gray-700 mb-1">State</label>
                    <input 
                      type="text" 
                      id="state" 
                      v-model="form.state" 
                      class="w-full px-3 py-2 border border-gray-300 rounded-md focus:outline-none focus:ring-2 focus:ring-primary"
                    />
                  </div>
                  <div>
                    <label for="zip" class="block text-sm font-medium text-gray-700 mb-1">ZIP Code</label>
                    <input 
                      type="text" 
                      id="zip" 
                      v-model="form.zip" 
                      class="w-full px-3 py-2 border border-gray-300 rounded-md focus:outline-none focus:ring-2 focus:ring-primary"
                    />
                  </div>
                </div>
              </div>
  
              <h2 class="text-lg font-medium text-gray-900 mb-4">Payment Method</h2>
              <div class="space-y-3 mb-6">
                <div class="flex items-center">
                  <input 
                    type="radio" 
                    id="creditCard" 
                    value="creditCard" 
                    v-model="form.paymentMethod"
                    class="h-4 w-4 text-primary focus:ring-primary border-gray-300"
                  />
                  <label for="creditCard" class="ml-2 block text-sm text-gray-700">Credit Card</label>
                </div>
                <div class="flex items-center">
                  <input 
                    type="radio" 
                    id="paypal" 
                    value="paypal" 
                    v-model="form.paymentMethod"
                    class="h-4 w-4 text-primary focus:ring-primary border-gray-300"
                  />
                  <label for="paypal" class="ml-2 block text-sm text-gray-700">PayPal</label>
                </div>
                <div class="flex items-center">
                  <input 
                    type="radio" 
                    id="applePay" 
                    value="applePay" 
                    v-model="form.paymentMethod"
                    class="h-4 w-4 text-primary focus:ring-primary border-gray-300"
                  />
                  <label for="applePay" class="ml-2 block text-sm text-gray-700">Apple Pay</label>
                </div>
                <div class="flex items-center">
                  <input 
                    type="radio" 
                    id="googlePay" 
                    value="googlePay" 
                    v-model="form.paymentMethod"
                    class="h-4 w-4 text-primary focus:ring-primary border-gray-300"
                  />
                  <label for="googlePay" class="ml-2 block text-sm text-gray-700">Google Pay</label>
                </div>
              </div>
  
              <div v-if="form.paymentMethod === 'creditCard'" class="space-y-4">
                <div>
                  <label for="cardNumber" class="block text-sm font-medium text-gray-700 mb-1">Card Number</label>
                  <input 
                    type="text" 
                    id="cardNumber" 
                    v-model="form.cardNumber" 
                    placeholder="1234 5678 9012 3456"
                    class="w-full px-3 py-2 border border-gray-300 rounded-md focus:outline-none focus:ring-2 focus:ring-primary"
                  />
                </div>
                <div class="grid grid-cols-2 gap-4">
                  <div>
                    <label for="expiry" class="block text-sm font-medium text-gray-700 mb-1">Expiry Date</label>
                    <input 
                      type="text" 
                      id="expiry" 
                      v-model="form.expiry" 
                      placeholder="MM/YY"
                      class="w-full px-3 py-2 border border-gray-300 rounded-md focus:outline-none focus:ring-2 focus:ring-primary"
                    />
                  </div>
                  <div>
                    <label for="cvv" class="block text-sm font-medium text-gray-700 mb-1">CVV</label>
                    <input 
                      type="text" 
                      id="cvv" 
                      v-model="form.cvv" 
                      placeholder="123"
                      class="w-full px-3 py-2 border border-gray-300 rounded-md focus:outline-none focus:ring-2 focus:ring-primary"
                    />
                  </div>
                </div>
              </div>
  
              <!-- Payment Buttons -->
              <!-- Apple Pay Button -->
              <div v-if="form.paymentMethod === 'applePay'" class="mt-6">
                <button 
                  @click="processApplePay"
                  class="w-full bg-black text-white py-3 px-4 rounded-md hover:bg-gray-800 focus:outline-none focus:ring-2 focus:ring-offset-2 focus:ring-gray-500 transition-colors flex items-center justify-center"
                >
                  <svg class="h-5 w-5 mr-2" viewBox="0 0 24 24" fill="currentColor">
                    <path d="M17.0425 10.4717C17.0142 8.25792 18.8225 7.11 18.8858 7.0675C17.8142 5.5075 16.1708 5.27 15.5858 5.25C14.1425 5.1 12.7425 6.1325 12.0108 6.1325C11.2675 6.1325 10.1108 5.265 8.8775 5.2925C7.2775 5.32 5.7775 6.2675 4.9425 7.7675C3.2108 10.8175 4.5108 15.3075 6.1775 17.4825C6.9975 18.5475 7.9658 19.7475 9.2358 19.6975C10.4775 19.6425 10.9425 18.8925 12.4425 18.8925C13.9308 18.8925 14.3658 19.6975 15.6608 19.6675C16.9958 19.6425 17.8358 18.5775 18.6308 17.5025C19.5658 16.2675 19.9425 15.0525 19.9575 14.9925C19.9275 14.9775 17.0758 13.9425 17.0425 10.4717Z" />
                    <path d="M14.7425 3.7725C15.4075 2.9475 15.8575 1.8225 15.7275 0.6825C14.7575 0.7275 13.5425 1.3425 12.8475 2.1525C12.2275 2.8725 11.6775 4.0275 11.8225 5.1375C12.9075 5.2275 14.0475 4.5975 14.7425 3.7725Z" />
                  </svg>
                  Pay with Apple Pay
                </button>
              </div>
  
              <!-- Google Pay Button -->
              <div v-if="form.paymentMethod === 'googlePay'" class="mt-6">
                <button 
                  @click="processGooglePay"
                  class="w-full bg-white border border-gray-300 py-3 px-4 rounded-md hover:bg-gray-50 focus:outline-none focus:ring-2 focus:ring-offset-2 focus:ring-gray-500 transition-colors flex items-center justify-center"
                >
                  <svg class="h-5 w-5 mr-2" viewBox="0 0 24 24">
                    <path d="M12.545 10.239v3.821h5.445c-0.712 2.315-2.647 3.972-5.445 3.972-3.332 0-6.033-2.701-6.033-6.033s2.701-6.032 6.033-6.032c1.498 0 2.866 0.549 3.921 1.453l2.814-2.814c-1.798-1.677-4.203-2.701-6.735-2.701-5.445 0-9.878 4.433-9.878 9.878s4.433 9.879 9.878 9.879c8.631 0 10.51-8.206 9.687-11.422h-9.687z" fill="#4285F4"/>
                    <path d="M12.545 10.239v3.821h5.445c-0.712 2.315-2.647 3.972-5.445 3.972-3.332 0-6.033-2.701-6.033-6.033s2.701-6.032 6.033-6.032c1.498 0 2.866 0.549 3.921 1.453l2.814-2.814c-1.798-1.677-4.203-2.701-6.735-2.701-5.445 0-9.878 4.433-9.878 9.878s4.433 9.879 9.878 9.879c8.631 0 10.51-8.206 9.687-11.422h-9.687z" fill="#EA4335" transform="translate(3.5, 0)"/>
                    <path d="M12.545 10.239v3.821h5.445c-0.712 2.315-2.647 3.972-5.445 3.972-3.332 0-6.033-2.701-6.033-6.033s2.701-6.032 6.033-6.032c1.498 0 2.866 0.549 3.921 1.453l2.814-2.814c-1.798-1.677-4.203-2.701-6.735-2.701-5.445 0-9.878 4.433-9.878 9.878s4.433 9.879 9.878 9.879c8.631 0 10.51-8.206 9.687-11.422h-9.687z" fill="#FBBC05" transform="translate(7, 0)"/>
                    <path d="M12.545 10.239v3.821h5.445c-0.712 2.315-2.647 3.972-5.445 3.972-3.332 0-6.033-2.701-6.033-6.033s2.701-6.032 6.033-6.032c1.498 0 2.866 0.549 3.921 1.453l2.814-2.814c-1.798-1.677-4.203-2.701-6.735-2.701-5.445 0-9.878 4.433-9.878 9.878s4.433 9.879 9.878 9.879c8.631 0 10.51-8.206 9.687-11.422h-9.687z" fill="#34A853" transform="translate(10.5, 0)"/>
                  </svg>
                  Pay with Google Pay
                </button>
              </div>
  
              <!-- Standard Place Order Button (only for Credit Card and PayPal) -->
              <button 
                v-if="['creditCard', 'paypal'].includes(form.paymentMethod)"
                @click="placeOrder" 
                class="mt-6 w-full bg-primary text-white py-3 px-4 rounded-md hover:bg-primary-dark focus:outline-none focus:ring-2 focus:ring-offset-2 focus:ring-primary transition-colors"
              >
                Place Order
              </button>
            </div>
          </div>
        </div>
      
        <!-- Success Modal -->
        <Teleport to="body">
          <transition name="fade">
            <div v-if="paymentSuccessful" class="fixed inset-0 flex items-center justify-center z-50">
              <div class="fixed inset-0 bg-black bg-opacity-50" @click="closeModal"></div>
              <div class="bg-white rounded-lg p-8 max-w-md w-full mx-4 relative z-10 shadow-2xl">
                <div class="flex flex-col items-center text-center">
                  <div class="w-16 h-16 bg-green-100 rounded-full flex items-center justify-center mb-4">
                    <svg class="w-8 h-8 text-green-500" fill="none" stroke="currentColor" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg">
                      <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M5 13l4 4L19 7"></path>
                    </svg>
                  </div>
                  <h2 class="text-2xl font-bold text-gray-900 mb-2">Payment Successful!</h2>
                  <p class="text-gray-600 mb-6">Thank you for your order. We've received your payment and will process your order shortly.</p>
                  <button 
                    @click="closeModal" 
                    class="bg-primary text-white py-2 px-6 rounded-md hover:bg-primary-dark focus:outline-none focus:ring-2 focus:ring-offset-2 focus:ring-primary transition-colors"
                  >
                    Close
                  </button>
                </div>
              </div>
            </div>
          </transition>
        </Teleport>
      </div>
    </div>
  </template>
  
  <script setup>
  import { ref } from 'vue';
  
  // Form data
  const form = ref({
    firstName: '',
    lastName: '',
    email: '',
    phone: '',
    address: '',
    city: '',
    state: '',
    zip: '',
    paymentMethod: 'creditCard',
    cardNumber: '',
    expiry: '',
    cvv: ''
  });
  
  // Add this after the form ref
  const paymentSuccessful = ref(false);
  
  // Validate form function
  const validateForm = () => {
    if (!form.value.firstName || !form.value.lastName || !form.value.email) {
      alert('Please fill in all required fields');
      return false;
    }
    return true;
  };
  
  // Process Apple Pay
  const processApplePay = () => {
    if (!validateForm()) return;
    
    console.log('Processing Apple Pay payment...');
    
    // In a real app, you would integrate with the Apple Pay API here
    // For this example, we'll simulate a successful payment after a short delay
    setTimeout(() => {
      console.log('Apple Pay payment successful!');
      paymentSuccessful.value = true;
    }, 1000);
  };
  
  // Process Google Pay
  const processGooglePay = () => {
    if (!validateForm()) return;
    
    console.log('Processing Google Pay payment...');
    
    // In a real app, you would integrate with the Google Pay API here
    // For this example, we'll simulate a successful payment after a short delay
    setTimeout(() => {
      console.log('Google Pay payment successful!');
      paymentSuccessful.value = true;
    }, 1000);
  };
  
  // Place order function (for Credit Card and PayPal)
  const placeOrder = () => {
    if (!validateForm()) return;
    
    // In a real app, you would send this data to your server
    console.log('Order placed!', {
      customer: {
        firstName: form.value.firstName,
        lastName: form.value.lastName,
        email: form.value.email,
        phone: form.value.phone
      },
      shipping: {
        address: form.value.address,
        city: form.value.city,
        state: form.value.state,
        zip: form.value.zip
      },
      payment: {
        method: form.value.paymentMethod,
        details: form.value.paymentMethod === 'creditCard' ? {
          cardNumber: form.value.cardNumber,
          expiry: form.value.expiry,
          cvv: form.value.cvv
        } : {}
      }
    });
    
    // Show success modal
    paymentSuccessful.value = true;
  };
  
  // Close modal function
  const closeModal = () => {
    paymentSuccessful.value = false;
  };
  </script>
  
  <style scoped>
  /* Custom colors */
  :root {
    --color-primary: #4f46e5;
    --color-primary-dark: #4338ca;
  }
  
  .bg-primary {
    background-color: var(--color-primary);
  }
  
  .bg-primary-dark {
    background-color: var(--color-primary-dark);
  }
  
  .text-primary {
    color: var(--color-primary);
  }
  
  .ring-primary {
    --tw-ring-color: var(--color-primary);
  }
  
  .focus\:ring-primary:focus {
    --tw-ring-color: var(--color-primary);
  }
  
  .hover\:bg-primary-dark:hover {
    background-color: var(--color-primary-dark);
  }
  
  /* Add these transition styles */
  .fade-enter-active,
  .fade-leave-active {
    transition: opacity 0.3s ease;
  }
  
  .fade-enter-from,
  .fade-leave-to {
    opacity: 0;
  }
  </style>