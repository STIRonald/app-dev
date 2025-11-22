
#returnCarSelect {
    font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
    width: 100%;
    padding: 12px;
    border-radius: 12px;
    border: 1px solid var(--border);
    background: rgba(255, 255, 255, 0.6); /* glass */
    backdrop-filter: blur(8px);
    box-shadow: var(--shadow);
    outline: none;
    transition: all 0.25s ease;
    cursor: pointer;
}

/* Select focus */
#returnCarSelect:focus {
    border-color: var(--primary);
    box-shadow: 0 0 0 3px rgba(37, 99, 235, 0.3);
}

/* Options */
#returnCarSelect option {
    padding: 10px;
    border-bottom: 1px solid #e9e9e9;
    font-size: 15px;
}

#returnCarSelect option:hover {
    background-color: rgba(37, 99, 235, 0.15);
}

/* ===============================
   Enhanced Search Input Styling
================================= */
#returnCarSearch {
    width: 100%;
    padding: 12px;
    margin-bottom: 10px;
    border-radius: 12px;
    border: 2px solid #ddd;
    background: rgba(255, 255, 255, 0.7); /* glass */
    backdrop-filter: blur(8px);
    transition: border-color 0.3s, box-shadow 0.3s;
}

#returnCarSearch:focus {
    border-color: var(--primary);
    box-shadow: 0 0 0 3px rgba(37, 99, 235, 0.3);
    outline: none;
}
</style>

  </head>
<body>
    <div id="adminDashboard" class="dashboard hidden" >
    <aside class="sidebar">
      <div class="sidebar-header">
        <h2><image src = "assets/images/LOGOPROCAR.png" style = "width:190px ;height:auto;"></h2>
        
      </div>
      <ul class="sidebar-menu">
  <li><a href="#" class="active" onclick="showAdminSection('dashboard', event)">📊 Dashboard</a></li>
  <li><a href="#" onclick="showAdminSection('cars', event)">Manage Cars</a></li>
  <li><a href="#" onclick="showAdminSection('carplans', event)">Car Plans</a></li>
  <li><a href="#" onclick="showAdminSection('bookings', event)">Manage Bookings</a></li>
  <li><a href="#" onclick="showAdminSection('plans', event)">Rental Plans</a></li>
  <li><a href="#" onclick="showAdminSection('returns', event)">Returns</a></li>
  <li><a href="#" onclick="showAdminSection('payments', event)">Payments</a></li>
  <li><a href="#" onclick="showAdminSection('users', event)">👥 User Management</a></li>
</ul>
    </aside>
    <main class="main-content">
      <div class="topbar">
        <h1>Admin Dashboard</h1>
        <div class="user-menu">
          <div class="avatar" onclick="toggleAdminDropdown()">A</div>
          <div id="adminDropdown" class="dropdown">
            <div class="dropdown-item">
              <div>
                <div id="adminName">Admin</div>
                <small id="adminEmail">admin@email.com</small>
              </div>
            </div>
            <div class="dropdown-item" onclick="logout()">Logout</div>
          </div>
        </div>
      </div>
      
      
      
      <div class="content-area"> 


                        
           
      
      
      <!-- Add this Dashboard Section BEFORE adminCarsSection in login.php -->
<!-- Inside <div class="content-area"> after the opening tag -->
<div class="content-area">
<div id="adminDashboardSection">
  <!-- Stats Cards -->
  
      <div class="period-filter">
        <label>📅 View Period:</label>
        <button class="period-btn" onclick="changePeriod('week')">Last 7 Days</button>
        <button class="period-btn active" onclick="changePeriod('month')">This Month</button>
        <button class="period-btn" onclick="changePeriod('year')">This Year</button>
        </div>

  <div class="stats-grid">
    <div class="stat-card">
      <div class="stat-icon" style="background: #dad2c5;">💰</div>
      <div class="stat-content">
        <div class="stat-label">Total Revenue</div>
        <div class="stat-value" id="totalRevenue">₱0.00</div>
      </div>
    </div>
    
    <div class="stat-card">
      <div class="stat-icon" style="background: #dad2c5;">📅</div>
      <div class="stat-content">
        <div class="stat-label">Total Bookings</div>
        <div class="stat-value" id="totalBookings">0</div>
      </div>
    </div>
    
    <div class="stat-card">
      <div class="stat-icon" style="background: #dad2c5;">🚗</div>
      <div class="stat-content">
        <div class="stat-label">Active Rentals</div>
        <div class="stat-value" id="activeRentals">0</div>
      </div>
    </div>
    
    <div class="stat-card">
      <div class="stat-icon" style="background: #dad2c5;">⏳</div>
      <div class="stat-content">
        <div class="stat-label">Pending Bookings</div>
        <div class="stat-value" id="pendingBookings">0</div>
      </div>
    </div>
    
    <div class="stat-card">
      <div class="stat-icon" style="background: #dad2c5;">🚙</div>
      <div class="stat-content">
        <div class="stat-label">Total Cars</div>
        <div class="stat-value" id="totalCars">0</div>
      </div>
    </div>
    
    <div class="stat-card">
      <div class="stat-icon" style="background: #dad2c5;">✅</div>
      <div class="stat-content">
        <div class="stat-label">Available Cars</div>
        <div class="stat-value" id="availableCars">0</div>
      </div>
    </div>
    
    <div class="stat-card">
      <div class="stat-icon" style="background: #dad2c5;">👥</div>
      <div class="stat-content">
        <div class="stat-label">Total Customers</div>
        <div class="stat-value" id="totalCustomers">0</div>
      </div>
    </div>
    
    <div class="stat-card">
      <div class="stat-icon" style="background: #dad2c5;">📊</div>
      <div class="stat-content">
        <div class="stat-label">This Month Revenue</div>
        <div class="stat-value" id="monthRevenue">₱0.00</div>
      </div>
    </div>
    
    <div class="stat-card">
      <div class="stat-icon" style="background: #dad2c5;">📈</div>
      <div class="stat-content">
        <div class="stat-label">This Month Bookings</div>
        <div class="stat-value" id="monthBookings">0</div>
      </div>
    </div>
  </div>

  <!-- Charts Row -->
  <div class="charts-row">
    <div class="card chart-card">
      <div  class="card-header" >
        <h3  >Revenue Trend (Last 12 Months)</h3>
      </div>
      <div class="chart-container">
        <canvas id="revenueChart"></canvas>
      </div>
    </div>
    
    <div class="card chart-card">
      <div class="card-header">
        <h3>Bookings by Status</h3>
      </div>
      <div class="chart-container">
        <canvas id="bookingsChart"></canvas>
      </div>
    </div>
  </div>

  <!-- Popular Cars & Recent Activities -->
  <div class="dashboard-bottom-row">
    <div class="card">
      <div class="card-header">
        <h3>Most Popular Cars</h3>
      </div>
      <div class="table-container">
        <table>
          <thead>
            <tr>
              <th>#</th>
              <th>Car</th>
              <th>Plate No</th>
              <th>Bookings</th>
              <th>Revenue</th>
            </tr>
          </thead>
          <tbody id="popularCarsTable">
            <tr><td colspan="5" class="loading">Loading...</td></tr>
          </tbody>
        </table>
      </div>
    </div>
    
    <div class="card">
      <div class="card-header">
        <h3>Recent Activities</h3>
      </div>
      <div id="recentActivities" class="activities-container">
        <div class="loading">Loading...</div>
      </div>
    </div>
  </div>
</div>
      
      <!-- Manage Cars Section -->
        <div id="adminCarsSection" >
          <div class="card">
            <div class="card-header">
              <h3>Manage Cars</h3>
              <button class="btn btn-primary" onclick="openCarModal()">Add New Car</button>
            </div>
            <div class="table-container">
              <table>
                <thead>
                  <tr>
                    <th>ID</th>
                    <th>Brand</th>
                    <th>Model</th>
                    <th>Plate No</th>
                    <th>Daily Rate</th>
                    <th>Status</th>
                    <th>Actions</th>
                  </tr>
                </thead>
                <tbody id="carsTable">
                  <tr><td colspan="7" class="loading">Loading cars...</td></tr>
                </tbody>
              </table>
            </div>
          </div>
        </div>
           
        


        <!-- Car Plans Section (NEW) -->
        <div id="adminCarPlansSection" class="hidden">
          <div class="card">
            <div class="card-header">
              <h3>Car Plans (Link Cars to Rental Plans)</h3>
              <button class="btn btn-primary" onclick="openCarPlanModal()">Add Car Plan</button>
            </div>
            <div class="table-container">
              <table>
                <thead>
                  <tr>
                    <th>ID</th>
                    <th>Car</th>
                    <th>Plan</th>
                    <th>Final Rate</th>
                    <th>Actions</th>
                  </tr>
                </thead>
                <tbody id="carPlansTable">
                  <tr><td colspan="5" class="loading">Loading car plans...</td></tr>
                </tbody>
              </table>
            </div>
          </div>
        </div>

        <!-- Manage Bookings Section -->
        <div id="adminBookingsSection" class="hidden">
          <div class="card">
            <div class="card-header">
              <h3>Manage Bookings</h3>
            </div>
            <div class="table-container">
              <table>
                <thead>
                  <tr>
                    <th>ID</th>
                    <th>Customer</th>
                    <th>Car</th>                    
                    <th>Plan</th>
                    <th>Pickup/dilever</th>
                    <th>Start Date</th>
                    <th>End Date</th>
                    <th>Bill</th>
                    <th>Payment Method</th>
                    <th>Status</th>                   
                    <th>Actions</th>
                    
                  </tr>
                </thead>
                <tbody id="allBookingsTable">
                  <tr><td colspan="7" class="loading">Loading bookings...</td></tr>
                </tbody>
              </table>
            </div>
          </div>
        </div>

        <!-- Rental Plans Section -->
        <div id="adminPlansSection" class="hidden">
          <div class="card">
            <div class="card-header">
              <h3>Rental Plans</h3>
              <button class="btn btn-primary" onclick="openPlanModal()">Add New Plan</button>
            </div>
            <div class="table-container">
              <table>
                <thead>
                  <tr>
                    <th>ID</th>
                    <th>Plan Name</th>
                    <th>Description</th>
                    <th>Rate Multiplier</th>
                    <th>Actions</th>
                  </tr>
                </thead>
                <tbody id="plansTable">
                  <tr><td colspan="5" class="loading">Loading plans...</td></tr>
                </tbody>
              </table>
            </div>
          </div>
        </div>

        <!-- Returns Section -->
        <div id="adminReturnsSection" class="hidden">
          <div class="card">
            <div class="card-header">
              <h3>Returns</h3>
              <button class="btn btn-primary" onclick="openReturnModal()">Add Return</button>
            </div>
            <div class="table-container">
              <table>
                <thead>
                  <tr>
                    <th>ID</th>
                    <th>Car</th>
                    <th>Customer</th>
                    <th>Return Date</th>
                    <th>Fuel Level</th>
                    <th>Mileage</th>
                    <th>Extra Charges</th>
                  </tr>
                </thead>
                <tbody id="returnsTable">
                  <tr><td colspan="7" class="loading">Loading returns...</td></tr>
                </tbody>
              </table>
            </div>
          </div>
        </div>
       <!-- User Management Section -->
        <div id="adminUsersSection" class="hidden">
     <div class="card">
    <div class="card-header">
      <h3>User Management</h3>
    </div>
    <div class="table-container">
      <table>
        <thead>
          <tr>
            <th>ID</th>
            <th>Name</th>
            <th>Email</th>
            <th>Phone</th>
            <th>Driver License No</th>
            <th>Status</th>
            <th>Verified By</th>
            <th>Actions</th>
          </tr>
        </thead>
        <tbody id="usersTable">
          <tr><td colspan="8" class="loading">Loading users...</td></tr>
        </tbody>
      </table>
    </div>
  </div>
</div>
      
      <!-- Payments Section -->
<div id="adminPaymentsSection" class="hidden">
  <div class="card">
    <div class="card-header">
      <h3>Payments</h3>
      <button class="btn btn-primary" onclick="openPaymentModal()">Add Payment</button>
    </div>
    <div class="table-container">
      <table>
        <thead>
          <tr>
            <th>ID</th>
            <th>Booking ID</th>
            <th>Customer</th>
            <th>Car</th>
            <th>Amount</th>
            <th>Method</th>
            <th>Payment Date</th>
          </tr>
        </thead>
        <tbody id="paymentsTable">
          <tr><td colspan="7" class="loading">Loading payments...</td></tr>
        </tbody>
      </table>
    </div>
  </div>
    </div>
      
      
      
      
        </main>
      </div>


  


<!-- User Details Modal -->
<div id="userDetailsModal" class="modal">
  <div class="modal-content">
    <div class="modal-header">
      <h3>User Details</h3>
      <button class="close-btn" onclick="closeUserDetailsModal()">×</button>
    </div>
    <div id="userDetailsContent" class="modal-body">
      <!-- Filled dynamically by adminUsers.js -->
      <div class="loading">Loading user details...</div>
    </div>
  </div>
</div>

<!-- Rejection Modal -->
<div id="rejectionModal" class="modal">
  <div class="modal-content">
    <div class="modal-header">
      <h3>Reject Verification</h3>
      <button class="close-btn" onclick="closeRejectionModal()">×</button>
    </div>
    <form id="rejectionForm" class="modal-body">
      <input type="hidden" id="rejectionCustomerId">
      <div class="form-group">
        <label>Rejection Reason</label>
        <textarea id="rejectionReason" required></textarea>
      </div>
      <div style="margin-top:12px;">
        <button type="submit" class="btn btn-danger">Submit Rejection</button>
      </div>
    </form>
  </div>
</div>

 <!-- PAYMENT MODAL dala design ni -->
<div id="paymentModal" class="modal">
  <div class="modal-content">
    <div class="modal-header">
      <h3>Record Payment</h3>
      <button class="close-btn" onclick="closePaymentModal()">×</button>
    </div>
    <form id="paymentForm">
      <div class="form-group">
        <label>Booking ID</label>
        <input type="number" id="paymentBookingId" required>
        <small>Enter the booking ID to record payment for</small>
      </div>
      <div class="form-group">
        <label>Amount (₱)</label>
        <input type="number" id="paymentAmount" step="0.01" required>
      </div>
      <div class="form-group">
        <label>Payment Method</label>
        <select id="paymentMethod" required>
          <option value="cash">Cash</option>
          <option value="credit_card">Credit Card</option>
          <option value="debit_card">Debit Card</option>
          <option value="online">Online Payment</option>
        </select>
      </div>
      <button type="submit" class="btn btn-primary">Record Payment</button>
    </form>
  </div>
 </div>
 <!-- CAR MODAL WITH IMAGE UPLOAD -->
<div id="carModal" class="modal">
  <div class="modal-content">
    <div class="modal-header">
      <h3 id="carModalTitle">Add New Car</h3>
      <button class="close-btn" onclick="closeCarModal()">×</button>
    </div>
    <form id="carForm" onsubmit="event.preventDefault(); saveCarForm();">
      <input type="hidden" id="carId">
      
      <div class="form-group">
        <label>Brand</label>
        <input type="text" id="carBrand" required>
      </div>
      
      <div class="form-group">
        <label>Model</label>
        <input type="text" id="carModel" required>
      </div>
      
      <div class="form-group">
        <label>Plate Number</label>
        <input type="text" id="carPlate" required>
      </div>
      
      <div class="form-group">
        <label>Daily Rate (₱)</label>
        <input type="number" id="carRate" step="0.01" required>
      </div>
      
      <div class="form-group">
        <label>Status</label>
        <select id="carStatus">
          <option value="available">Available</option>
          <option value="rented">Rented</option>
          <option value="maintenance">Maintenance</option>
        </select>
      </div>
      
      <!-- Image Upload Section -->
      <div class="form-group">
        <label>Car Images (Upload up to 3 images)</label>
        <div class="image-upload-section">
          <!-- Image 1 -->
          <div class="image-upload-box">
            <label for="carImage1">Image 1</label>
            <div id="imagePreview1" class="image-preview" onclick="document.getElementById('carImage1').click()">
              <div class="upload-placeholder">📷 Image 1</div>
            </div>
            <input type="file" id="carImage1" accept="image/*" onchange="previewImage(this, 'imagePreview1')">
          </div>
          
          <!-- Image 2 -->
          <div class="image-upload-box">
            <label for="carImage2">Image 2</label>
            <div id="imagePreview2" class="image-preview" onclick="document.getElementById('carImage2').click()">
              <div class="upload-placeholder">📷 Image 2</div>
            </div>
            <input type="file" id="carImage2" accept="image/*" onchange="previewImage(this, 'imagePreview2')">
          </div>
          
          <!-- Image 3 -->
          <div class="image-upload-box">
            <label for="carImage3">Image 3</label>
            <div id="imagePreview3" class="image-preview" onclick="document.getElementById('carImage3').click()">
              <div class="upload-placeholder">📷 Image 3</div>
            </div>
            <input type="file" id="carImage3" accept="image/*" onchange="previewImage(this, 'imagePreview3')">
          </div>
        </div>
      </div>
      
      <button type="submit" class="btn btn-primary">Save Car</button>
    </form>
  </div>
</div>
  <!-- CAR PLAN MODAL (NEW)  dala design ni -->
  <div id="carPlanModal" class="modal">
    <div class="modal-content">
      <div class="modal-header">
        <h3 id="carPlanModalTitle">Link Car to Plan</h3>
        <button class="close-btn" onclick="closeCarPlanModal()">×</button>
      </div>
      <form id="carPlanForm">
        <input type="hidden" id="carPlanId">
        <div class="form-group">
          <label>Select Car</label>
          <select id="carPlanCarId" required>
            <option value="">Loading cars...</option>
          </select>
        </div>
        <div class="form-group">
          <label>Select Rental Plan</label>
          <select id="carPlanPlanId" required>
            <option value="">Loading plans...</option>
          </select>
        </div>
        <button type="submit" class="btn btn-primary">Save Car Plan</button>
      </form>
    </div>
  </div>
  <!-- PLAN MODAL  dala design ni -->
  <div id="planModal" class="modal">
    <div class="modal-content">
      <div class="modal-header">
        <h3 id="planModalTitle">Add New Plan</h3>
        <button class="close-btn" onclick="closePlanModal()">×</button>
      </div>
      <form id="planForm">
        <input type="hidden" id="planId">
        <div class="form-group">
          <label>Plan Name</label>
          <input type="text" id="planName" required>
        </div>
        <div class="form-group">
          <label>Description</label>
          <input type="text" id="planDescription">
        </div>
        <div class="form-group">
          <label>Rate Multiplier</label>
          <input type="number" id="planRate" step="0.01" value="1.0" required>
        </div>
        <button type="submit" class="btn btn-primary">Save Plan</button>
      </form>
    </div>
  </div>
<!-- RETURN MODAL - Updated with Car Selection -->
<div id="returnModal" class="modal">
    <div class="modal-content">
      <div class="modal-header">
        <h3>Record Return</h3>
        <button class="close-btn" onclick="closeReturnModal()">×</button>
      </div>
      <form id="returnForm" onsubmit="event.preventDefault(); saveReturnForm();">
        <!-- Car Selection with Search -->
        <div class="form-group">
          <label>Select Car to Return <span style="color: var(--danger);">*</span></label>
          <input 
            type="text" 
            id="returnCarSearch" 
            class="form-control" 
            placeholder="🔍 Search by plate number or car name..."
            onkeyup="filterRentedCars()"
            style="margin-bottom: 8px;">
          <select id="returnCarSelect" class="form-control" required size="5" style="min-height: 120px;">
            <option value="">Loading rented cars...</option>
          </select>
          <small style="color: #666; display: block; margin-top: 4px;">
            Shows only cars that are currently rented and not yet returned
          </small>
        </div>
        
        <div class="form-group">
          <label>Fuel Level <span style="color: var(--danger);">*</span></label>
          <select id="returnFuel" class="form-control" required>
            <option value="Full">Full</option>
            <option value="3/4">3/4</option>
            <option value="1/2">1/2</option>
            <option value="1/4">1/4</option>
            <option value="Empty">Empty</option>
          </select>
        </div>
        
        <div class="form-group">
          <label>Mileage (km)</label>
          <input type="number" id="returnMileage" class="form-control" placeholder="Enter current mileage">
        </div>
        
        <div class="form-group">
          <label>Damages (if any)</label>
          <textarea id="returnDamages" class="form-control" rows="3" placeholder="Describe any damages or issues..."></textarea>
        </div>
        
        <div class="form-group">
          <label>Extra Charges (₱)</label>
          <input type="number" id="returnExtra" class="form-control" step="0.01" value="0" placeholder="0.00">
          <small style="color: #666;">For damages, late fees, fuel charges, etc.</small>
        </div>
        
        <button type="submit" class="btn btn-primary">Record Return</button>
      </form>
    </div>
</div>


 <!-- Load main JavaScript file customer -->
  <script src="assets/js/utils.js"></script>
 
  <script src="assets/js/auth.js"></script>
  <script src="assets/js/customer.js"></script>
  <script src="assets/js/booking.js"></script>
 
 <script src="https://cdn.jsdelivr.net/npm/chart.js@4.4.0/dist/chart.umd.min.js"></script>
   <!-- Load main JavaScript file admin -->
  <script src="assets/js/adminCars.js"></script>
   <script src="assets/js/adminCarPlans.js"></script>
   <script src="assets/js/adminBookings.js"></script>
   <script src="assets/js/adminPlans.js"></script>
   <script src="assets/js/adminReturns.js"></script>
   <script src="assets/js/adminPayments.js"></script>
   <script src="assets/js/adminDashboard.js"></script>
   <script src="assets/js/UIHelperFunctions.js"></script>
   <!-- Load form listeners and setup last -->
   <script src="assets/js/formListeners.js"></script>
   <script src="assets/js/adminUsers.js"></script>
    <script src="assets/js/customerProfile.js"></script>
   
</body>
</html>
