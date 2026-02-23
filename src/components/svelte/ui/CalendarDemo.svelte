<section class="calendar-demo">
  <div class="calendar-card">
    <div class="calendar-header">
      <span class="md-label-medium">March 2026</span>
      <div class="calendar-actions">
        <button class="md-icon-btn">
          <span class="md-icon">chevron_left</span>
        </button>
        <button class="md-icon-btn">
          <span class="md-icon">chevron_right</span>
        </button>
      </div>
    </div>
    <div class="calendar-grid">
      <span>Mo</span><span>Tu</span><span>We</span><span>Th</span><span>Fr</span><span>Sa</span><span>Su</span>
      <span class="muted">24</span><span class="muted">25</span><span class="muted">26</span><span class="muted">27</span><span class="muted">28</span><span>1</span><span>2</span>
      <span>3</span><span>4</span><span>5</span><span>6</span><span>7</span><span>8</span><span>9</span>
      <span>10</span><span>11</span><span class="active">12</span><span>13</span><span>14</span><span>15</span><span>16</span>
      <span>17</span><span>18</span><span>19</span><span>20</span><span>21</span><span>22</span><span>23</span>
      <span>24</span><span>25</span><span>26</span><span>27</span><span>28</span><span>29</span><span>30</span>
      <span>31</span><span class="muted">1</span><span class="muted">2</span><span class="muted">3</span><span class="muted">4</span><span class="muted">5</span><span class="muted">6</span>
    </div>
  </div>
  <div class="calendar-notes">
    <p class="md-body-small">Use the calendar to preview date-driven components.</p>
  </div>
</section>

<style>
  .calendar-demo {
    display: grid;
    grid-template-columns: minmax(240px, 320px) 1fr;
    gap: 16px;
  }

  .calendar-card {
    padding: 16px;
    border-radius: 20px;
    background-color: var(--md-sys-color-surface-container);
    border: 1px solid var(--md-sys-color-outline-variant);
  }

  .calendar-header {
    display: flex;
    justify-content: space-between;
    align-items: center;
    margin-bottom: 12px;
  }

  .calendar-actions {
    display: flex;
    gap: 6px;
  }

  .calendar-grid {
    display: grid;
    grid-template-columns: repeat(7, 1fr);
    gap: 6px;
    text-align: center;
    font-size: 12px;
  }

  .calendar-grid span {
    padding: 8px 0;
    border-radius: 10px;
    color: var(--md-sys-color-on-surface);
  }

  .calendar-grid span.muted {
    color: var(--md-sys-color-on-surface-variant);
  }

  .calendar-grid span.active {
    background-color: var(--md-sys-color-primary);
    color: var(--md-sys-color-on-primary);
  }

  .calendar-notes {
    padding: 16px;
    border-radius: 16px;
    border: 1px dashed var(--md-sys-color-outline-variant);
    background-color: var(--md-sys-color-surface-container-high);
  }

  .calendar-notes p {
    margin: 0;
    color: var(--md-sys-color-on-surface-variant);
  }

  @media (max-width: 720px) {
    .calendar-demo {
      grid-template-columns: 1fr;
    }
  }
</style>
