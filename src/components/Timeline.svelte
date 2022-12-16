<div class="wrapper">
  <ul class="timeline">
    <li>
      <details class="panel">
        <summary>
          <slot name="role" /> @ <slot name="org" />
        </summary>
        <p>
          <slot name="description" />
        </p>
      </details>
    </li>
    <li>
        <details class="panel">
          <summary>
            <slot name="role" /> @ <slot name="org" />
          </summary>
          <p>
            <slot name="description" />
          </p>
        </details>
      </li>
  </ul>
</div>
