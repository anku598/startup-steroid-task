<template>
  <div class="table-container">
    <table>
      <thead>
        <tr>
          <th scope="col">Name</th>
          <th scope="col">File</th>
          <th scope="col">Category</th>
          <th scope="col">Author</th>
          <th scope="col">Status</th>
        </tr>
      </thead>
      <tbody>
        <tr>
          <td data-label="Account">Annual Report</td>
          <td data-label="Due Date">04/01/2016</td>
          <td data-label="Amount">$1,190</td>
          <td data-label="Period">Raydoan</td>
          <td data-label="status" class="status sucess">
            <button>Send</button>
          </td>
        </tr>
        <tr>
          <td scope="row" data-label="Account">Business Plan</td>
          <td data-label="Due Date">03/01/2016</td>
          <td data-label="Amount">$2,443</td>
          <td data-label="Period">Jacob</td>
          <td data-label="status" class="status error">
            <button>Pending</button>
          </td>
        </tr>
        <tr>
          <td scope="row" data-label="Account">Marketing Tool</td>
          <td data-label="Due Date">03/01/2016</td>
          <td data-label="Amount">$1,181</td>
          <td data-label="Period">Diana Methews</td>
          <td data-label="status" class="status sucess">
            <button>Send</button>
          </td>
        </tr>
      </tbody>
    </table>
  </div>
</template>

<script setup></script>

<style lang="scss" scoped>
table {
  border-collapse: collapse;
  margin: 0;
  padding: 0;
  width: 100%;
  table-layout: fixed;
}

thead {
  text-align: left;
}

table tr {
  padding: 0.35em;
}

table th,
table td {
  padding: 0.625em;
}

table th {
  @include res-font(14, 18, 360, 1920);
  font-weight: 700;
  letter-spacing: 0.1em;
  margin-bottom: 1.2rem;
  text-transform: capitalize;
}

@media screen and (max-width: 600px) {
  table {
    border: 0;
  }

  table caption {
    font-size: 1.3em;
  }

  table thead {
    border: none;
    clip: rect(0 0 0 0);
    height: 1px;
    margin: -1px;
    overflow: hidden;
    padding: 0;
    position: absolute;
    width: 1px;
  }

  table tr {
    display: block;
    margin-bottom: 0.625em;
  }

  table td {
    display: block;
    font-size: 0.8em;
    text-align: right;
  }

  table td::before {
    /*
    * aria-label has no advantage, it won't be read inside a table
    content: attr(aria-label);
    */
    content: attr(data-label);
    float: left;
    font-weight: bold;
    text-transform: uppercase;
  }

  table td:last-child {
    border-bottom: 0;
  }
}

.status {
  button {
    padding: 0.8rem 1rem;
    border-radius: 10px;
    background: #f5f5f5;
    color: #000;
    border: none;
    cursor: pointer;
    border: none;
    outline: none;
    @include res-font(14, 18, 360, 1920);
    font-weight: 500;
    width: 100%;
    &:focus {
      outline: none;
    }
  }

  &.sucess {
    button {
      background: #a4ffa4;
    }
  }

  &.error {
    button {
      background: #f18888;
      color: #fff;
    }
  }
}
</style>
